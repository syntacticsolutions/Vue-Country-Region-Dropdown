<template>
    <select
        @change="$emit('change', $event)"
        @input="$emit('input', $event)"
        :placeholder="placeholder"
        :value="value">
        <option v-for="(obj, slug) in regions" :key="slug" :value="obj.regionShortCode">{{ obj.regionName }}</option>
    </select>
</template>

<script>
import CountryRegionData from '../fixtures/countries.js'

const C = {
  DISPLAY_TYPE_FULL: 'full',
  DISPLAY_TYPE_SHORT: 'short',
  REGION_LIST_DELIMITER: '|',
  SINGLE_REGION_DELIMITER: '~'
}

export default {
    name: 'v-region-dropdown',
    props: ['country', 'placeholder', 'value'],
    computed: {
        regions () {
            if (!this.country) {
                return []
            }
            let regions = []

            CountryRegionData.forEach((i) => {
                if (i[1] === this.country) {
                    regions = i
                }
            })

            if (!regions || regions.length === 1) {
                console.error('Error. Unknown country passed: ' + this.country + '. If you\'re passing a country shortcode, be sure to include countryValueType="short" on the RegionDropdown')
                return []
            }
            return regions[2]
                .split(C.REGION_LIST_DELIMITER)
                .map((regionPair) => {
                    let [regionName, regionShortCode = null] = regionPair.split(C.SINGLE_REGION_DELIMITER)
                    return { regionName, regionShortCode }
                })
        }
    }
}
</script>


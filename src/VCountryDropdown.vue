<template>
    <select
        @change="$emit('change', $event)"
        @input="$emit('input', $event)"
        :placeholder="placeholder"
        :value="value">
        <option v-for="(name, slug) in countries" :key="slug" :value="name[1]">{{ name[0] }}</option>
    </select>
</template>

<script>

import CountryRegionData from '../fixtures/countries.js'

export default {
    name: 'v-country-dropdown',
    props: ['whitelist', 'blacklist', 'placeholder', 'value'],
    data: () => ({
        countries: []
    }),
    methods: {
        filterCountries (countries, whitelist, blacklist) {
            let filteredCountries = countries

            if (whitelist && whitelist.length > 0) {
                filteredCountries = countries.filter(([, countrySlug]) => { return whitelist.indexOf(countrySlug) > -1 })
            }
            else if (blacklist && blacklist.length > 0) {
                filteredCountries = countries.filter(([, countrySlug]) => { return blacklist.indexOf(countrySlug) === -1 })
            }

            return filteredCountries
        }
    },
    mounted () {
        this.countries = this.filterCountries(CountryRegionData, this.$props.whitelist, this.$props.blacklist)
    }
}
</script>

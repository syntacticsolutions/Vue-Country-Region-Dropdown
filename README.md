# Getting Started

0. ```npm install vue-country-region-dropdown```

0. Getting Started:
```import Vue from 'vue' ```
```import VueCountryRegion from 'vue-country-region-dropdown'```
```Vue.use(VueCountryRegion)```



0. Country Dropdown
# Usage:

```<v-country-dropdown```
        ```:blacklist="blacklist"```
        ```placeholder="Select a Country"```
        ```:value="billing_country"```
        ```v-model="billing_country" /> ```

# Props:

`blacklist`: (optional) an array of country shortcodes that should be omitted from the dropdown

`value`: (optional)the country shortcode that belongs to the value that should be shown on mounted

0. Region Dropdown
# Usage:

```` <v-region-dropdown ```
    ```:country="billing_country"```
    ```v-model="billing_state"``` 
    ```:value="billing_state"```
    ```placeholder="Select a Region"/>```

#Props:

`country`: The country code from `v-country-dropdown`
`value`: (optional) the region shortcode of a region to be shown on load





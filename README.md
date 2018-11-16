# Getting Started


0. ```npm install vue-country-region-dropdown```

0. ```import Vue from 'vue' ```
0. ```import VueCountryRegion from 'vue-country-region-dropdown'```
0. ```Vue.use(VueCountryRegion)```



# Country Dropdown
0. Usage:

```<v-country-dropdown```
        ```:blacklist="blacklist"```
        ```placeholder="Select a Country"```
        ```:value="billing_country"```
        ```v-model="billing_country" /> ```

0. Props:

`blacklist`: (optional) an array of country shortcodes that should be omitted from the dropdown

`value`: (optional)the country shortcode that belongs to the value that should be shown on mounted

# Region Dropdown
0. Usage:

<pre><code>
    <v-region-dropdown
        :country="billing_country"
        v-model="billing_state"
        :value="billing_state"
        placeholder="Select a Region"/>
</code></pre>

0. Props:

`country`: The country code from `v-country-dropdown`
`value`: (optional) the region shortcode of a region to be shown on load





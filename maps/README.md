# Google Map for Nuxt.js

Sample location object

```javascript
var location = {
    lat: 9.9312,
    lng: 76.2673,
    label: "Kochi, India"
}
```

Usage

```javascript

<template>
    <Map :location="location" />
</template>

<script>
import Map from '@/components/nuxt-js-google-map-component'

export default {
    components: {
        Map
    },
    data() {
        return {
            location = {
                lat: 9.9312,
                lng: 76.2673,
                label: "Kochi, India"
            }
        }
    }
}
</script>
```

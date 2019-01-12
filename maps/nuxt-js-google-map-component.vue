<template>
  <div id="map"/>
</template>

<script>
export default {
    props: {
        location: {
            type: Object,
            default: () => {}
        }
    },
    head() {
        return {
            script: [
                {
                    src:
                        'https://maps.googleapis.com/maps/api/js?key={google-key}'
                }
            ]
        }
    },
    mounted() {
        var position = this.location.geometry

        var map = new google.maps.Map(document.getElementById('map'), {
            zoom: 16,
            center: position
        })
        var infowindow = new google.maps.InfoWindow({
            content: this.location.label
        })

        var marker = new google.maps.Marker({
            position: position,
            map: map,
            title: this.location.label
        })
        marker.addListener('click', function() {
            infowindow.open(map, marker)
        })
    }
}
</script>
<style>
#map {
    width: 100%;
    height: 300px;
}
</style>

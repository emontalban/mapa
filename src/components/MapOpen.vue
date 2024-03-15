<template>
  <div id="container">
    <div id="mapContainer"></div>
  </div>
 </template>

 <script>
import "leaflet/dist/leaflet.css";
import L from "leaflet";

export default {
 name: "MapOpen",
 data() {
   return{
     center: [43.0645024,-3.1331241,8.75]
   }},
 methods: {
   setupLeafletMap: function () {
     const mapDiv = L.map("mapContainer").setView(this.center, 13);
     L.tileLayer('https://{s}.tile.opentopomap.org/{z}/{x}/{y}.png', {
	maxZoom: 17,
	attribution: 'Map data: &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, <a href="http://viewfinderpanoramas.org">SRTM</a> | Map style: &copy; <a href="https://opentopomap.org">OpenTopoMap</a> (<a href="https://creativecommons.org/licenses/by-sa/3.0/">CC-BY-SA</a>)'
}
     ).addTo(mapDiv);
   },
 },
 mounted() {
   this.setupLeafletMap();
 },
};
</script>

<style scoped>
#mapContainer {
  margin: 0 auto;
  width: 50%;
  min-height: 400px;
  max-height: 500px;
  height: 100%;
}
</style>




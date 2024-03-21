<template>
  <div id="container">
    <div id="mapContainer"></div>
  </div>
 </template>

 <script>
import "leaflet/dist/leaflet.css";
import L from "leaflet";
import  'leaflet.markercluster';
import "leaflet-defaulticon-compatibility";
import "leaflet-defaulticon-compatibility/dist/leaflet-defaulticon-compatibility.css";
import markerIconUrl from '@/assets/img/marker-icon-2x-red.png';
import markerShadowUrl from '@/assets/img/marker-shadow.png';

import {iconoRojo} from '@/assets/iconos/icono.js';
import 'leaflet.markercluster/dist/MarkerCluster.css';
import 'leaflet.markercluster/dist/MarkerCluster.Default.css';

import '../style/color.css';
//C:\OneDrive\Escritorio\vuemap\mapvue\src\style\color.css



export default {
 name: "MapOpen",
 //data() {
   //return{
     //center: [43.2739667,-2.9226687,12.5]
  // }},


  
 methods: {
   setupLeafletMap: function () {
     //const mapDiv = L.map("mapContainer").setView(this.center, 13);
     const mapDiv = L.map("mapContainer").setView([43.2739667,-2.9226687,12.], 13);
     L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
      }).addTo(mapDiv);
    
      const markers = L.markerClusterGroup({
        iconCreateFunction: function (cluster) {
            const markers = cluster.getAllChildMarkers();
            let isRed = false;

            // Check if any marker in the cluster has a bindPopup with content '2'
            markers.forEach(function (marker) {
                if (marker.getPopup().getContent() === '2') {
                    isRed = true;
                }
            });

            if (isRed) {
              return L.divIcon({
                className: 'marker-cluster-red ',
                html: '<div class="marker-cluster-red">' + markers.length + '</div>'
               });
              } else {
             return L.divIcon({
                className: 'marker-cluster-green ',
                html: '<div class="marker-cluster-green">'
                 + markers.length + '</div>'
              });
            }
        }
    });
       
     L.marker([43.287, -2.891]).addTo(markers).bindPopup('1');
     L.marker([43.294, -2.891]).addTo(markers).bindPopup('1');
     L.marker([43.293, -2.891]).addTo(markers).bindPopup('1');
     L.marker([43.290, -2.891]).addTo(markers).bindPopup('1');
     L.marker([43.288, -2.879],{icon:redIcon}).addTo(markers).bindPopup('2');
     L.marker([43.290, -2.855],{icon:blackIcon}).addTo(markers).bindPopup('3');
     L.marker([43.292, -2.840],{icon:greenIcon}).addTo(markers).bindPopup('4');
     L.marker([43.296, -2.890],{icon:blueIcon}).addTo(markers).bindPopup('1');
     L.marker([43.283, -2.911],{icon:goldIcon}).addTo(markers).bindPopup('5');
     L.marker([43.266, -2.911],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.266, -2.912],{icon:iconoRojo}).addTo(markers).bindPopup('2');
     L.marker([43.266, -2.911],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.266, -2.911],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.256, -2.921],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.246, -2.931],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     L.marker([43.226, -2.951],{icon:violetIcon}).addTo(markers).bindPopup('6');
     
     
    
     


     mapDiv.addLayer(markers);
    
    }
    
 },
 mounted() {
   this.setupLeafletMap();
 },
 
};
const redIcon = new L.Icon({
        iconUrl: markerIconUrl,
        shadowUrl: markerShadowUrl,
        iconSize: [25, 41],
        iconAnchor: [12, 41],
        popupAnchor: [1, -34],
        shadowSize: [41, 41]
      });
/*
var redIcon = new L.Icon({
  iconUrl: 'https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-2x-red.png',
  shadowUrl: 'https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/images/marker-shadow.png',
  iconSize: [25, 41],
  iconAnchor: [12, 41],
  popupAnchor: [1, -34],
  shadowSize: [41, 41]
});
*/
var blueIcon = new L.Icon({
  iconUrl: 'https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-2x-orange.png',
  shadowUrl: 'https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/images/marker-shadow.png',
  iconSize: [25, 41],
  iconAnchor: [12, 41],
  popupAnchor: [1, -34],
  shadowSize: [41, 41]
});
var greenIcon = new L.Icon({
  iconUrl: 'https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-2x-green.png',
  shadowUrl: 'https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/images/marker-shadow.png',
  iconSize: [25, 41],
  iconAnchor: [12, 41],
  popupAnchor: [1, -34],
  shadowSize: [41, 41]
});
var goldIcon = new L.Icon({
  iconUrl: 'https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-2x-gold.png',
  shadowUrl: 'https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/images/marker-shadow.png',
  iconSize: [25, 41],
  iconAnchor: [12, 41],
  popupAnchor: [1, -34],
  shadowSize: [41, 41]
});
var violetIcon = new L.Icon({
  iconUrl: 'https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-2x-violet.png',
  shadowUrl: 'https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/images/marker-shadow.png',
  iconSize: [25, 41],
  iconAnchor: [12, 41],
  popupAnchor: [1, -34],
  shadowSize: [41, 41]
});
var blackIcon = new L.Icon({
	iconUrl: 'https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-2x-black.png',
	shadowUrl: 'https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/images/marker-shadow.png',
	iconSize: [25, 41],
	iconAnchor: [12, 41],
	popupAnchor: [1, -34],
	shadowSize: [41, 41]
});

</script>

<style scoped>
#mapContainer {
 width: 80vw;
 height: 100vh;
 margin: 0 auto;
}
</style>






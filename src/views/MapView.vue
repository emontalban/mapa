<template>
    <div>
        <h1> Mapa</h1>
    <MapOpen></MapOpen>
    </div>
</template>
<script>
import MapOpen from '../components/MapOpen.vue'; 

export default {
  name:'MapView',
  components: {
    MapOpen,
  }
}
</script>
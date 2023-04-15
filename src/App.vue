<template>
  <Map></Map>
</template>
 
<script>
import Map from './components/Map.vue'
 
export default {
  name: 'App',
  components: {
    Map
  }
}
</script>
 
<style>
@import url('../node_modules/ol/ol.css');
@import url('../node_modules/font-gis/css/font-gis.css');

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
 
html, body, #map, #app {
  height: 100%;
  margin: 0;
  padding: 0;
}

.ol-control button{
  color: #8A1946;
  background-color: #f9f6ed;
}

.ol-control button:hover{
  color: #f9f6ed;
  background-color: #8A1946;
}

.ol-side-panel-tabs, .ol-side-panel-tabs > button, .ol-side-panel-tabs > button.active {
  color: #8A1946;
  background-color: #f9f6ed;
}

.ol-side-panel-tabs > button:hover {
  color:#f9f6ed;
  background-color: #8A1946;
}

.ol-side-panel-content {
  background-color:#f9f6ed ;
}

.ol-side-panel-close:hover {
  color: #8A1946;
}

</style>
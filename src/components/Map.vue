<template>
    <div id="map"></div>
</template>

<script>
import { SidePanel } from 'ol-side-panel';
import { Map, View } from 'ol';
import { Tile as TileLayer } from 'ol/layer';
import { OSM } from 'ol/source';

export default {
    name: 'Map',
    mounted() {
        this.map = new Map({
            target: 'map',
            layers: [
                new TileLayer({
                    source: new OSM()
                })
            ],
            view: new View({
                center: [0, 0],
                zoom: 2
            })
        })
        let sidePanel = new SidePanel();
        this.map.addControl(sidePanel);

        let layersPane = sidePanel.definePane({
            paneId: 'layers',
            name: "Layers",
            icon: '<i class="fg-regular-shape-pt"></i>'
        });
    }
}
</script>

<style>
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
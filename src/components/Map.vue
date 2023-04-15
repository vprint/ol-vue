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
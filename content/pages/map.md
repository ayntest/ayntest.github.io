Title: Map

<link rel="stylesheet" href="/css/leaflet.css" />
<script src="/javascript/leaflet.js"></script>

<div style="height:480px" id="map">
<script>
var mapsize = 8256;
var map = L.map('map', {
    maxZoom:24,
    minZoom:22,
    crs: L.CRS.Simple
}).setView([0,0], 23);
var southWest = map.unproject([0, mapsize], map.getMaxZoom());
var northEast = map.unproject([mapsize, 0], map.getMaxZoom());
map.setMaxBounds(new L.LatLngBounds(southWest, northEast));
L.tileLayer('http://maps.ayntest.net/tiles/{z}/map_{x}_{y}.png', {
            maxZoom: 24,
            tileSize: 344,
}).addTo(map);
map.setView(map.unproject([mapsize/4,mapsize/4]));
</script>

</div>
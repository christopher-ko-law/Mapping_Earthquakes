# Mapping_Earthquakes

## Purpose
To map earthquake data for the past 7 days over the globe and relate the data to the position of the tectonic plates. This map was created using JS, Leaflet.js, and geoJSON data.
<br>
Please navigate to the Earthquake_Challenge folder to view all relevant files.

## Results
This map includes: 
* 3 separate tile layers: Street, Satellite, Dark
* 3 separate data layers: Earthquakes, Tectonic Plates, Major Earthquakes

Below is a screenshot of the map:<br>
![Screenshot](/images/map.png)

Each deliverable below can be seen in the above screenshot.

### Deliverable 1
The tectonic plate layer was added and stylized to be orange with a weight of 2.
```    
function styleTechtonicPlate(feature) {
    return {
        color: "orange",
        stroke: true,
        weight: 2
    };
};
```

### Deliverable 2
The major earthquake layer was added and 3 different colours were used to define the major earthquakes.
```    
function getColor(magnitude) {
    if (magnitude > 6) {
        return "#ff0000";
    }
    if (magnitude > 5) {
        return "#ea2c2c";
    }
    return "#ea822c";
}
```

### Deliverable 3
A dark map was added.
```
// Deliverable 3 - Creating a 3rd tile layer.
let dark = L.tileLayer('https://api.mapbox.com/styles/v1/mapbox/dark-v10/tiles/{z}/{x}/{y}?access_token={accessToken}', {
	attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery (c) <a href="https://www.mapbox.com/">Mapbox</a>',
	maxZoom: 18,
	accessToken: API_KEY
});

// Create a base layer that holds all three maps.
let baseMaps = {
  "Streets": streets,
  "Satellite": satelliteStreets,
  "Dark": dark
};
```


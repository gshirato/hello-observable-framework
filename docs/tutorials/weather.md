---
theme: dashboard
---

# Weather report

## Data Import

```js
const forecast = FileAttachment("./data/forecast.json").json();
```

```js
display(forecast);
```

```js
import * as L from "npm:leaflet";
```


## Meanwhile, the maps in London


```js
const div = display(document.createElement("div"));
div.style = "height: 400px;";

const map = L.map(div)
  .setView([51.505, -0.09], 13);

L.tileLayer("https://tile.openstreetmap.org/{z}/{x}/{y}.png")
  .addTo(map);

L.marker([51.5, -0.09])
  .addTo(map)
  .bindPopup("A nice popup<br> indicating a point of interest.")
  .openPopup();
```

## Some plots
```js
import temperaturePlot from './components/forecast.js'
```

```html
<div class="grid grid-cols-2">
  <div class="card grid-colspan-2">${resize((width) => temperaturePlot(forecast, {width}))}</div>
  <div class="card">three</div>
  <div class="card">four</div>
</div>
```
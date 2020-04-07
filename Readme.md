# d3js - MANDATORY TASK
# PINNING LOCATION - UPDATE MAPVIEW

In this task we want to add to a map of Spain pinning as circle to show the cases of coronavirus in each region. The size of the circles depend on the number of cases, futhermore, we are going to add buttons to the chart to compare two dates and update our map.

![map affected coronavirus](./content/MapaAnimado.png "affected coronavirus")

To performance this our departure point will be the following repository of Lemoncode:

https://github.com/Lemoncode/d3js-typescript-examples/tree/master/02-maps/02-pin-location-scale


## Steps

- Clone the project from: https://github.com/FernndMR/d3js-mandatory.git
- Execute

```bash
npm install
```
```bash
npm start
```
- Add the stats of current cases of covid 10 in stat file:

_./src/stats.css_

```typescritp
export interface StatsEntry {
  name: string;
  value: number;
}

export const base_stats: StatsEntry[] = [
  {
    name: "Comunidad de Madrid",
    value: 587
  },
  {
    name: "La Rioja",
    value: 102
  },
  {
    name: "Andalucía",
    value: 54
  },
  {
    name: "Cataluña",
    value: 101
  },
  {
    name: "Comunidad Valenciana",
    value: 50
  },
  {
    name: "Región de Murcia",
    value: 5
  },
  {
    name: "Extremadura",
    value: 7
  },
  {
    name: "Castilla-La Mancha",
    value: 26
  },
  {
    name: "País Vasco",
    value: 148
  },
  {
    name: "Cantabria",
    value: 12
  },
  {
    name: "Principado de Asturias",
    value: 10
  },
  {
    name: "Galicia",
    value: 18
  },
  {
    name: "Aragón",
    value: 32
  },
  {
    name: "Castilla y León",
    value: 40
  },
  {
    name: "Islas Canarias",
    value: 24
  },
  {
    name: "Islas Baleares",
    value: 11
  },
  {
    name: "Comunidad Foral de Navarra",
    value: 13
  }
];

export const nowadays_stats: StatsEntry[] = [
  {
    name: "Comunidad de Madrid",
    value: 40469
  },
  {
    name: "La Rioja",
    value: 2846
  },
  {
    name: "Andalucía",
    value: 8767
  },
  {
    name: "Cataluña",
    value: 28323
  },
  {
    name: "Comunidad Valenciana",
    value: 7443
  },
  {
    name: "Región de Murcia",
    value: 1283
  },
  {
    name: "Extremadura",
    value: 2116
  },
  {
    name: "Castilla-La Mancha",
    value: 11077
  },
  {
    name: "País Vasco",
    value: 9021
  },
  {
    name: "Cantabria",
    value: 1501
  },
  {
    name: "Principado de Asturias",
    value: 1679
  },
  {
    name: "Galicia",
    value: 6331
  },
  {
    name: "Aragón",
    value: 3449
  },
  {
    name: "Castilla y León",
    value: 9581
  },
  {
    name: "Islas Canarias",
    value: 1725
  },
  {
    name: "Islas Baleares",
    value: 1369
  },
  {
    name: "Comunidad Foral de Navarra",
    value: 3355
  }
];
```

- Import the stats to our index.ts

```typescript
import { latLongCommunities } from "./communities";
```

- Print two buttons that update the map depending on the stats:

_./src/index.html_

```typescript
<html>
  <head>
    <link rel="stylesheet" type="text/css" href="./map.css" />
    <link rel="stylesheet" type="text/css" href="./base.css" />
  </head>
  <body>
    <div>
      <button id="initial">07/03/2020</button>
      <button id="current">07/04/2020</button>
    </div>
    <div>
      <script src="./index.ts"></script>
    </div>
  </body>
</html>
```
_./src/index.ts_

```typescript
document
  .getElementById("initial")
  .addEventListener("click", function handleBaseResults() {
    updateMap(base_stats);
  });

document
  .getElementById("current")
  .addEventListener("click", function handleCurrentResults() {
    updateMap(nowadays_stats);
  });
  ```
  - Set a style to our map:
  
  _./scr/map.css_
  
  ```typescript
  .country {
  stroke-width: 1;
  stroke: #2f4858;
  fill: #e2db79;
}

.affected-marker {
  stroke-width: 1;
  stroke: #bc5b40;
  fill: #f88f70;
  fill-opacity: 0.7;
}
```
**Enjoy it!**



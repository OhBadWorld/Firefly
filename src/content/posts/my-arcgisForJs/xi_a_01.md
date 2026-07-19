---
title: arcgis for js 绘制线段
published: 2023-07-19 19:38:05
tags: [vue, arcgis for js, javascript, 可视化]
category: webgis
---

### 代码

```js
let polyline = {
  type: "polyline", // autocasts as new Polyline()
  paths: [
    [-111.3, 52.68],
    [-98, 49.5],
    [-93.94, 29.89],
  ],
};

let polylineSymbol = {
  type: "simple-line", // autocasts as SimpleLineSymbol()
  color: [226, 119, 40],
  width: 4,
};

let polylineAtt = {
  Name: "Keystone Pipeline",
  Owner: "TransCanada",
};

let polylineGraphic = new Graphic({
  geometry: polyline,
  symbol: polylineSymbol,
  attributes: polylineAtt,
});

view.graphics.add(polylineGraphic);
```

## 参考文档

1. https://developers.arcgis.com/javascript/latest/api-reference/esri-Graphic.html

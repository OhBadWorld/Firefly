---
title: arcgis for js  地图点击事件, 拾取经纬度
published: 2023-07-21 19:38:05
tags: [vue, arcgis for js, javascript, 可视化]
category: webgis
---

### 代码

```js
view
  .on("click", (event) => {
    const position = event.mapPoint;

    // 清空一下
    view.graphics.removeAll();

    // 构建显示信息
    textSymbol.symbolLayers[0].text =
      position.longitude.toFixed(4) +
      "," +
      position.latitude.toFixed(4) +
      "," +
      position.z.toFixed(2);
    //添加到地图
    view.graphics.add(
      new Graphic({
        geometry: position,
        symbol: textSymbol,
      }),
    );
  })
  .catch((error) => {
    textSymbol.symbolLayers[0].text =
      "Elevation query failed (" + error.message + ")";
  });
```

## 参考文档

1. https://blog.csdn.net/weixin_46177488/article/details/125893212

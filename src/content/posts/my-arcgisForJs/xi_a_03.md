---
title: arcgis for js 将 图层 至于 最顶层
published: 2023-07-24 19:38:05
tags: [vue, arcgis for js, javascript, 可视化]
category: webgis
---

场景： 地图 要实现 图层的切换，矢量地图 和 影像地图的切换， 但是切换的时候， 点位分布所在的图层 就被 切换之后的地图图层（矢量 或 影像） 给 覆盖住了，看不到了，这个时候，就需要把 点位分布的图层 置于最顶层。

使用 地图的 reorder() 方法

### 代码

```js
...
    // 加载高德影像图
    addGaoDeImg() {
      // 1.0 移除高德矢量图
      this.mapView.map.remove(this.gdVectorLayer);
      // 1.1 加载高德影像图
      this.mapView.map.add(this.gdImgLayer.gaodeImg);
      this.mapView.map.add(this.gdImgLayer.gaodeAnno);
      // 1.2 刷新图层，将图层置于最顶层
      this.mapView.map.reorder(this.graphicsLayerGatherLayer);
      this.mapView.map.reorder(this.graphicsLayerNameLayer);
    },
    // 加载高德矢量图
    addGaoDeVector() {
      // 1.0 移除高德影像图
      this.mapView.map.remove(this.gdImgLayer.gaodeImg);
      this.mapView.map.remove(this.gdImgLayer.gaodeAnno);
      // 1.1 加载高德矢量图
      this.mapView.map.add(this.gdVectorLayer);
      // 1.2 刷新图层，将图层置于最顶层
      this.mapView.map.reorder(this.graphicsLayerGatherLayer);
      this.mapView.map.reorder(this.graphicsLayerNameLayer);
    },
...

```

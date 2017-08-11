# Leaflet-TrackPlayback-Control

基于leaflet+canvas+vuejs实现的海上船舶轨迹回放插件，支持轨迹的播放、暂停、快进、快退操作以及上万个轨迹点的显示和上千条轨迹的回放。

[查看Demo](https://linghuam.github.io/TrackPlayback/dist/index.html)

## Remind
说明：该库来源于[~~SituationPlayback~~](https://github.com/linghuam/SituationPlayback)（已弃用），将会在该库完成轨迹回放功能，并完善成各个版本。

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## Data
采用geojson格式数据
```
{
  "type": "Feature",
  "geometry": {
    "type": "MultiPoint",
    "coordinates": [/*array of [lng,lat] coordinates*/]
  },
  "properties": {
    "time": [/*array of UNIX timestamps*/]
  }
}
```

## Problem
* 时间轴不能连续读秒，而是根据数据时间间隔变化，用户体验不好。
* 播放过程中缩放地图如果动画还在继续，船舶无法立即回到原位。
* 没有采用插值算法，而是根据真实数据播放，有时播放效果较差。但是采用插值算法，又会产生数据量过大问题。

### 以上问题自己正在思索解决，如果有好的解决建议,[欢迎提问](https://github.com/linghuam/TrackPlayback/issues)

## 拓展阅读
* [曲线轨迹动画原理](http://www.tuicool.com/articles/zaeQf22)
* [WebGIS中使用ZRender实现轨迹前端动态播放特效](http://www.cnblogs.com/naaoveGIS/p/6718822.html)


## License

[MIT license](https://opensource.org/licenses/mit-license.php)

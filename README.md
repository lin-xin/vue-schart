# vue-schart 

> :bar_chart: Vue.js wrapper for sChart.js

<p>
  <a href="https://www.npmjs.com/package/vue-schart"><img src="https://img.shields.io/npm/dm/vue-schart.svg" alt="Downloads"></a>
  <a href="https://www.npmjs.com/package/vue-schart"><img src="https://img.shields.io/npm/v/vue-schart.svg" alt="Version"></a>
  <a href="https://www.npmjs.com/package/vue-schart"><img src="https://img.shields.io/npm/l/vue-schart.svg" alt="License"></a>
  <br>
</p>

Support for use at the mobile. Support vue.js 1.x & 2.x

## Usage

Install:

```
npm install vue-schart -S
```

Use in component:

```html
<template>
    <div id="app">
        <schart class="wrapper" canvasId="canvas" :options="options" />
    </div>
</template>
<script>
	import Schart from 'vue-schart';
	export default {
		data() {
			return {
				options: {
					type: "bar",
					title: {
						text: "最近一周各品类销售图"
					},
					bgColor: "#fbfbfb",
					labels: ["周一", "周二", "周三", "周四", "周五"],
					datasets: [
						{
							label: "家电",
							fillColor: "rgba(241, 49, 74, 0.5)",
							data: [234, 278, 270, 190, 230]
						},
						{
							label: "百货",
							data: [164, 178, 190, 135, 160]
						},
						{
							label: "食品",
							data: [144, 198, 150, 235, 120]
						}
					]
				}
			}
		},
		components:{
			Schart
		}
	}
</script>

<style>
.wrapper{
	width: 7rem;
	height: 5rem;
}
</style>
```
## Options

Refer to [the documentation for sChart.js](https://lin-xin.gitee.io/example/schart/).

## License
[MIT license](https://github.com/lin-xin/vue-schart/blob/master/LICENCE).
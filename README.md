# vue-schart 

> :bar_chart: Vue.js wrapper for sChart.js

<p>
  <a href="https://www.npmjs.com/package/vue-schart"><img src="https://img.shields.io/npm/dm/vue-schart.svg" alt="Downloads"></a>
  <a href="https://www.npmjs.com/package/vue-schart"><img src="https://img.shields.io/npm/v/vue-schart.svg" alt="Version"></a>
  <a href="https://www.npmjs.com/package/vue-schart"><img src="https://img.shields.io/npm/l/vue-schart.svg" alt="License"></a>
  <br>
</p>

Support for use at the mobile. Support vue.js 1.x & 2.x

[interactive demo](http://blog.gdfengshuo.com/example/#/vue-schart)

## Usage

Install:

```
npm install vue-schart -S
```

Use in component:

```html
<template>
    <div id="app">
        <schart class="wrapper" :canvasId="canvasId" :type="type" :data="data" :options="options"></schart>
    </div>
</template>
<script>
import Schart from 'vue-schart';
	export default {
		data() {
			return {
				canvasId: 'myCanvas',
				type: 'bar',
				data: [
					{name: '2014', value: 1342},
					{name: '2015', value: 2123},
					{name: '2016', value: 1654},
					{name: '2017', value: 1795},
				],
				options: {
					title: 'Total sales of stores in recent years'
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

Refer to [the documentation for sChart.js](http://blog.gdfengshuo.com/example/sChart/).

## Demo

![demo](http://blog.gdfengshuo.com/example/sChart/static/img/demo.png)

## License
[MIT license](https://github.com/lin-xin/vue-schart/blob/master/LICENCE).
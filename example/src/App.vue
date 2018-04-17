<template>
  <div id="app">
    <schart class="wrapper" :canvasId="canvasId" :type="type" :data="data" :options="options"></schart>
		<schart class="wrapper" canvasId="canvas1" type="pie" :data="data" :options="options"></schart>
    <button @click="change">change</button>
  </div>
</template>

<script>
import Schart from './vue-schart.vue';
export default {
  name: 'app',
  data () {
    return {
			flag: false,
      canvasId: 'myCanvas',
			type: 'bar',
			data: [
				{name: '2014', value: 1342},
				{name: '2015', value: 2123},
				{name: '2016', value: 841},
        {name: '2015', value: 2123},
				{name: '2016', value: 589},
				{name: '2017', value: 1795},
			],
			options: {
				title: 'Total sales of stores in recent years',
				bottomPadding: 30
			}
    }
  },
  components:{
		Schart
	},
  methods: {
    change(){
      this.data = [
        {name: '2015', value: 2123},
				{name: '2016', value: 589},
				{name: '2017', value: 1795},
        {name: '2014', value: 1342},
			];
			this.type = 'line';
			this.$set(this.options, 'title', '哈哈哈哈哈哈')
    }
  }
}
</script>
<style>
.wrapper{
	width: 500px;
	height: 400px;
  /* width: 7rem;
  height: 5rem; */
}
</style>

<template>
    <div id="app">
        <schart class="wrapper" canvasId="canvas" :options="options"></schart>
        <button @click="change('bar')">change to bar</button>
        <button @click="change('line')">change to line</button>
        <button @click="change('pie')">change to pie</button>
        <button @click="change('ring')">change to ring</button>
    </div>
</template>

<script>
import Schart from "./vue-schart";
export default {
    name: "app",
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
        };
    },
    created() {
        this.getData();
    },
    components: {
        Schart
    },
    methods: {
        getData() {
            setTimeout(() => {
                const data = [
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
                ];
                this.$set(this.options1, "datasets", data);
            }, 1000);
        },
        change(type) {
            this.$set(this.options1, "type", type);
        }
    }
};
</script>
<style>
.wrapper {
    width: 500px;
    height: 400px;
}
</style>

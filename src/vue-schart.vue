<template>
    <div>
        <canvas :id="canvasId"></canvas>
    </div>
</template>

<script>
    import sChart from 'schart.js';
    export default {
        data() {
            return {
                schart: null,
                opt: {}
            }
        },
        props: {
            canvasId: {
                type: String,
                default: ''
            },
            type: {
                type: String,
                default: 'bar',
            },
            data: {
                type: Array,
                default: [],
            },
            options: {
                type: Object,
                required: false
            }
        },
        mounted() {
            this.renderChart();
        },
        methods: {
            renderChart(){
                this.schart = null;
                this.opt = this.options;
                if(!this.width || !this.height){
                    if(!this.opt){
                        this.opt = {autoWidth: true};
                    }else{
                        this.opt['autoWidth'] = true;
                    }
                }
                this.schart = new sChart(this.canvasId, this.type, this.data, this.opt);
            }
        },
        watch: {
            data(){
                this.renderChart();
            },
            options(){
                this.renderChart();
            },
            type(){
                this.renderChart();
            }
        }
    }
</script>
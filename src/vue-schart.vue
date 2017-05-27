<template>
    <div>
        <canvas :id="canvasId" :width="width" :height="height"></canvas>
    </div>
</template>

<script>
    import sChart from 'schart.js';
    export default {
        data() {
            return {}
        },
        props: {
            canvasId: {
                type: String,
                default: ''
            },
            width: {
                type: [String, Number],
                default: 500
            },
            height: {
                type: [String, Number],
                default: 400
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
            var self = this;
            new sChart(self.canvasId, self.type, self.data, self.options);
        }
    }
</script>
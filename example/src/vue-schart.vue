<template>
    <div>
        <canvas :id="canvasId"></canvas>
    </div>
</template>

<script>
import Schart from "schart.js";
export default {
    props: {
        canvasId: {
            type: String,
            default: "",
            required: true
        },
        options: {
            type: Object,
            required: true
        }
    },
    mounted() {
        this.renderChart();
    },
    methods: {
        renderChart() {
            if (!this.checkOptions()) {
                return;
            }
            const opt = { ...this.options };
            new Schart(this.canvasId, opt);
        },
        checkOptions() {
            const opt = this.options;
            if (!opt.datasets || !opt.datasets.length) {
                return false;
            }
            if (!opt.labels || !opt.labels.length) {
                return false;
            }
            return true;
        }
    },
    watch: {
        options: {
            handler(newValue, oldValue) {
                this.renderChart();
            },
            deep: true
        }
    }
};
</script>
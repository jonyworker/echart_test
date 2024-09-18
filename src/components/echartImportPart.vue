<script setup>
import { onMounted } from "vue";
import * as echarts from "echarts/core";
import { BarChart } from "echarts/charts";
import {
    TitleComponent,
    TooltipComponent,
    GridComponent,
    DatasetComponent,
    TransformComponent,
} from "echarts/components";
import { LabelLayout, UniversalTransition } from "echarts/features";
import { CanvasRenderer } from "echarts/renderers";

// Register necessary components
echarts.use([
    TitleComponent,
    TooltipComponent,
    GridComponent,
    DatasetComponent,
    TransformComponent,
    BarChart,
    LabelLayout,
    UniversalTransition,
    CanvasRenderer,
]);

// Function to initialize the chart
const initChart = () => {
    const myChart = echarts.init(document.getElementById("part"));
    myChart.setOption({
        title: {
            text: "ECharts 入门示例",
        },
        tooltip: {},
        xAxis: {
            data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"],
        },
        yAxis: {},
        series: [
            {
                name: "销量",
                type: "bar",
                data: [5, 20, 36, 10, 10, 20],
            },
        ],
    });
};

// Initialize chart on component mount
onMounted(() => {
    initChart();
});
</script>

<template>
    <div id="part" style="width: 600px; height: 400px"></div>
</template>

<style scoped></style>

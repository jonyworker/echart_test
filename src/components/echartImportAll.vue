<script setup>
import { onMounted } from "vue";
import * as echarts from "echarts";

const initChart = () => {
    const myChart = echarts.init(document.getElementById("main"));
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

onMounted(() => {
    initChart();
});
</script>

<template>
    <div id="main" style="width: 600px; height: 400px"></div>
</template>

<style scoped></style>

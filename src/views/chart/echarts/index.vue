<!--
 * @Author: Topskys
 * @Date: 2022-10-06 11:22:08
 * @LastEditTime: 2022-10-06 17:15:58
-->
<template>
    <div>
        <div id="ECharts" style="width:1000px ; height:600px;"></div>
    </div>
</template>

<script>
import * as echarts from 'echarts';
export default {
    name: "ECharts",
    data() {
        return {

        }
    },
    mounted() {
        this.initECharts()
    },
    methods: {
        initECharts() {
            // 准备好实例化ECharts的DOM
            let dom = document.querySelector('#ECharts')
            // 实例化ECharts
            let chart = echarts.init(dom)
            // 数据集
            let data = [
                ["衣服", 10, 20, "x", 30],
                ["直播", 12, 15, "y", 16],
                ["游戏", 1, 26, "z", 10],
                ["电影", 12, 40, "t", 36],
                ["逛街", 33, 6, "e", 13],
            ]
            // 配置项与接入数据
            chart.setOption({
                // 设置字符集
                dataset: {
                    source: data // 数据源
                },
                title: {
                    text: "数据可视化ECharts", textStyle: {
                        color: "#000"
                    },
                    subtext: "子标题",
                    // subtextStyle: {
                    //     color: "cyan"
                    // },
                    // left: "center",
                },
                xAxis: {
                    // data: ["衣服", "直播", "游戏", "电影", "逛街"],
                    type: "category",// 该属性可让散点之间的距离看起来均匀些
                },
                yAxis: [
                    // 双y轴，可通过yAxisIndex来配置哪个图表要哪条y轴 
                    {
                        // 显示y轴
                        axisLine: {
                            show: true
                        },
                        // 显示y轴刻度
                        axisTick: {
                            show: true
                        }
                    },
                    { // 显示y轴
                        axisLine: {
                            show: true
                        },
                        // 显示y轴刻度
                        axisTick: {
                            show: true
                        }
                    }
                ],
                // 系列
                series: [
                    {
                        type: "bar",// 图表类型
                        // data: [10, 20, 15, 28, 3],// 接入数据
                        encode: {
                            y: 1,// 字符集的第二列
                        },
                        color: "green",
                        name: "柱状图", 
                        yAxisIndex:0,
                    },
                    {
                        type: "line",// 折线图
                        // data: [10, 20, 15, 28, 3],
                        encode: {
                            y: 2
                        },
                        color: "red",
                        name: "折线图",
                        yAxisIndex: 1,
                    },
                    {
                        type: "pie",// 饼图
                        // data: [{ name: "a", value: 10 }, { name: "b", value: 20 }, { name: "c", value: 15 }, { name: "d", value: 28 }, { name: "e", value: 3 }],
                        width: 200,
                        height: 200,
                        top: 60,
                        left: 250,
                        radius: 40,
                        encode: {
                            // 饼图旁边的文字
                            itemName: 3,
                            value: 4,
                        },
                        name: "饼图",
                    },
                    {
                        type: "scatter",
                        data: [[10, 20], [30, 10], [14, 34], [8, 10], [23, 9]],
                        name: "散点图",
                    }
                ],
                // 点击图标任一点弹出提示组件
                tooltip: {
                    textStyle: {
                        color: 'black'
                    }
                },
                // 图表系列切换，需要在每个系列设置name
                legend: {
                    data: ["柱状图", "折线图", "饼图", "散点图"]
                },
                // 工具箱组件
                toolbox: {
                    show: true,
                    feature: {
                        dataZoom: {
                            yAxisIndex: "none"
                        },
                        dataView: {
                            readOnly: false
                        },
                        magicType: {
                            type: ["bar", "line", "pie"]
                        }, restore: {},
                        saveAsImage: {},
                    }
                },
                // 缩放查看
                dataZoom: {},
                // 调整图标布局
                grid: {
                    // top: 80,
                    // left: 50,
                    // bottom: 80,
                    // right: 30,
                }
            })
        }
    }

}
</script>

<style>

</style>
<!--
 * @Author: Topskys
 * @Date: 2022-10-05 22:20:07
 * @LastEditTime: 2022-10-06 10:39:28
-->
<template>
    <div>
        <!-- canvas画布:是HTML5中新增的一个特性，双闭合标签-->
        <!-- canvas标签默认宽度与高度300* 150 -->
        <!-- 浏览器认为canvas标签是一张图片-->
        <!--给canvas画布添加文本内容没有任何意义-->
        <!--给canvas标签添加子节点没有任何意义的-->
        <!--你想操作canvas画布:画布当中绘制图形、显示一个文字，都必须通过Js完成-->
        <!-- canvas标签的w|h务必通过canvas标签属性width | height设置-->
        <!--切记不能通过样式去设置画布的宽度与高度-->
        <canvas width="1300" height="500"></canvas>
    </div>
</template>

<script>
export default {
    name: "canvas",
    mounted() {
        this.initCanvas()
    },
    methods: {
        initCanvas() {
            // canvas标签任何操作务必通过Js完成，canvas绘制完成是一张图片（像素点）
            //通过JS当中"笔"去完成
            let canvas = document.querySelector('canvas');
            //获取画布的笔【上下文】
            let ctx = canvas.getContext('2d');

            // 绘制三角形
            //绘制线段:绘制线段的起点的设置
            ctx.moveTo(800, 100)
            // 其他点的设置
            ctx.lineTo(900, 200)
            ctx.lineTo(900, 100)
            // 设置图片填充颜色
            ctx.fillStyle = "gold"
            ctx.fill()
            // 设置线段填充颜色
            ctx.strokeStyle = "red"
            ctx.lineWidth = "2"
            // 设置起点与终点绘制一起
            ctx.closePath()
            // stroke()绘制线段
            ctx.stroke()


            // 绘制矩形， 方式一(x,y,w,h)
            ctx.strokeRect(950, 200, 100, 200)
            // 绘制矩形，方式二(x,y,w,h)，默认填充黑色
            ctx.fillStyle = 'skyblue' // 填充颜色必须在绘制图片之前
            ctx.fill()
            ctx.fillRect(1100, 200, 100, 200)
            ctx.stroke()

            // 绘制圆形
            ctx.beginPath()
            // 绘制圆形的方法：(x,y,r,起始弧度,结束弧度,是否逆时针绘制)，360°=2*PI*弧
            ctx.arc(500, 100, 50, 0, 2 * Math.PI, true)
            ctx.fillStyle = 'green'
            ctx.fill()
            ctx.stroke()

            // 绘制半圆
            ctx.beginPath()
            // 绘制圆形的方法：(x,y,r,起始弧度,结束弧度,是否逆时针绘制)，360°=2*PI*弧
            ctx.arc(660, 100, 50, 0, 1 * Math.PI, false)
            ctx.fillStyle = 'black'
            ctx.fill()
            ctx.stroke()

            // 清除画布与绘制文字
            // 清除画布:(x,y,w,h)，根据参数可部分清除
            // ctx.clearRect(0, 0, 300, 200)
            // 绘制文字
            // 设置文字样式
            ctx.font = "20px 微软雅黑"
            ctx.fillStyle = "blue"
            ctx.fillText("Canvas", 50, 20)

            // 绘制柱状图
            ctx.font = "16px 微软雅黑"
            ctx.fillStyle = "#000"
            ctx.fillText("柱状图", 50, 50)
            // 设置线段填充颜色
            ctx.strokeStyle = "black"
            ctx.lineWidth = "1"
            // 绘制线段
            ctx.moveTo(100, 100)
            ctx.lineTo(100, 400)
            ctx.lineTo(700, 400)
            ctx.stroke()
            // 绘制其他线段
            ctx.moveTo(100, 100)
            ctx.lineTo(700, 100)
            ctx.fillText("150", 65, 110)
            ctx.moveTo(100, 160)
            ctx.lineTo(700, 160)
            ctx.fillText("120", 65, 170)
            ctx.moveTo(100, 220)
            ctx.lineTo(700, 220)
            ctx.fillText("90", 65, 230)
            ctx.moveTo(100, 280)
            ctx.lineTo(700, 280)
            ctx.fillText("60", 65, 290)
            ctx.moveTo(100, 340)
            ctx.lineTo(700, 340)
            ctx.fillText("30", 65, 350)
            ctx.stroke()
            // 绘制水平轴底部刻度线段
            ctx.moveTo(250, 400)
            ctx.lineTo(250, 410)
            // 底部文字
            ctx.fillText("食品", 170, 420)
            ctx.moveTo(400, 400)
            ctx.lineTo(400, 410)
            ctx.fillText("数码", 310, 420)
            ctx.moveTo(550, 400)
            ctx.lineTo(550, 410)
            ctx.fillText("服饰", 450, 420)
            ctx.fillText("箱包", 600, 420)
            ctx.stroke()
            // 绘制柱状矩形
            ctx.fillStyle = 'red'
            ctx.fillRect(120, 130, 100, 270)
            ctx.fillRect(270, 150, 100, 250)
            ctx.fillRect(420, 200, 100, 200)
            ctx.fillRect(570, 200, 100, 200)
        },
    }
}
</script>

<style scoped>
canvas {
    border: 1px solid #000;
}
</style>
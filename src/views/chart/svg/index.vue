<template>
    <div>
        <!-- SVG是一种基于XML的图像文件格式，它的英文全称为Scalable Vector Graphics，意思为可缩放的矢量图形。
基本的SVG元素
你可以深入SVG复杂的细节，但这对我们即将创建的图标不是必须的。以下列表涵盖了我们将用到的构建块。
<svg〉包裹并定义整个矢量图。<svg>标签之于矢量图就如同〈html>标签之于一个web页面。
<line>创建—条直线。
<polyline>创建折线。
<rect>创建矩形。
<circle>创建圆。
<ellipse>创建圆和椭圆。
<polygon>创建多边形。
<path>通过指定点以及点和点之间的线来创建任意形状。 -->

        <!-- svg为双闭合标签，默认宽高300*150，svg绘制图形务必在svg标签内部使用绘制图形 -->
        <svg class="svg-container">
            <!-- stroke：线段颜色填充 -->
            <line x1="100" y1="100" x2="200" y2="200" stroke="red"></line>
            <!-- “,”可放可不放 -->
            <polyline points="300 300,50 100,120,400,20,20" fill-opacity="0.5" stroke="cyan"></polyline>
            <rect x="400" y="400" width="100" height="200" fill="pink"></rect>
            <circle cx="370" cy="95" r="70" style="stroke:aqua;fill:none;"></circle>
            <!-- 绘制圆形||椭圆 -->
            <ellipse cx="500" cy="500" rx="100" ry="50" style="fill:bisque;"></ellipse>
            <!-- 绘制多边形 -->
            <polygon points="600 100,300 400,750 150" stroke="blue" fill-opacity="0"></polygon>
            <!-- 绘制任意图形 -->
            <path fill-opacity="0.5" stroke="skyblue" id="
            M 10 10
            L 20 400
            L 30 120
            L 40 66
            L 50 99
            L 60 120
            L 70 99
            Z 
            "></path>

        </svg>

    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.svg-container {
    width: 800px;
    height: 800px;
}
</style>
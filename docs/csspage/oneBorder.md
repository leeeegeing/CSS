# 1px边框

!> 分辨率比较低的屏幕下显示1px的边框会显得模糊，通过`::before`或`::after`和`transform`模拟细腻的1px边框

<vuep template="#oneBorder"></vuep>

<script v-pre type="text/x-template" id="oneBorder">

<template>
<div>
	<div class="onepx-border normal">常规 1px 边框</div>
	<div class="onepx-border thin">绘制 1px 边框</div>
</div>
</template>

<style>
.onepx-border {
	margin-top: 10px;
	width: 200px;
	height: 80px;
	cursor: pointer;
	line-height: 80px;
	text-align: center;
	font-weight: bold;
	font-size: 16px;
	color: #42b983;
}
.onepx-border:first-child {
  margin-top: 0;
}
.normal {
	border: 1px solid #42b983;
}
.thin {
	position: relative;
}
.thin::after {
  position: absolute;
  left: 0;
  top: 0;
  border: 1px solid #42b983;
  width: 200%;
	height: 200%;
  content: "";
  transform: scale(.5);
  transform-origin: left top;
}
</style>

<script>
</script>
</script>


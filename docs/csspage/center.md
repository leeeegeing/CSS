# 居中的几种方法

## 水平居中 margin

!> 利用外边距自动对齐


<vuep template="#center1"></vuep>

<script v-pre type="text/x-template" id="center1">
<template>
  <div class="center-wrapper"></div>
</template>
<style>
.center-wrapper{
  margin: 0 auto;
  width: 200px;
  height: 200px;
  background: #eee;
}
</style>

<script>
</script>
</script>


## 水平居中 text-align

!> 需要注意的是 `text-align` 只对行内元素起作用


<vuep template="#center2"></vuep>

<script v-pre type="text/x-template" id="center2">
<template>
  <div class="center-wrapper">Hello World!!</div>
</template>
<style>
.center-wrapper{
  margin: 0 auto;
  width: 100%;
  line-height: 50px;
  text-align: center;
  color: #333;
  background: #eee;
}
</style>

<script>
</script>
</script>

## 水平垂直居中 position + margin

!> 前提是需要知道垂直居中的宽高才能实现

<vuep template="#center3"></vuep>

<script v-pre type="text/x-template" id="center3">
<template>
  <div class="center-wrapper">
    <img class="center-img" src="http://images.leegeing.cn/hexoImg/demo.jpeg"/>
  </div>
</template>
<style>
.center-wrapper{
  position: relative;
  width: 100%;
  height: 250px;
  text-align: center;
  color: #333;
  background: #eee;
}

.center-img{
  position: absolute;
  top: 50%;
  left: 50%;
  margin-top: -50px;
  margin-left: -50px;
  width: 100px;
  height: 100px;
  object-fit: cover;
}
</style>

<script>
</script>
</script>

## 水平垂直居中 position + margin

!> 和上一种方法的不同之处在于，不用受到宽高的限制

<vuep template="#center4"></vuep>

<script v-pre type="text/x-template" id="center4">
<template>
  <div class="center-wrapper">
    <img class="center-img" src="http://images.leegeing.cn/hexoImg/demo.jpeg"/>
  </div>
</template>
<style>
.center-wrapper{
  position: relative;
  width: 100%;
  height: 250px;
  text-align: center;
  color: #333;
  background: #eee;
}

.center-img{
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
  width: 100px;
  height: 100px;
  object-fit: cover;
}
</style>

<script>
</script>
</script>

## 水平垂直居中 position + transfrom

!> translate(x,y) 水平方向和垂直方向同时移动

<vuep template="#center5"></vuep>

<script v-pre type="text/x-template" id="center5">
<template>
  <div class="center-wrapper">
    <img class="center-img" src="http://images.leegeing.cn/hexoImg/demo.jpeg"/>
  </div>
</template>
<style>
.center-wrapper{
  position: relative;
  width: 100%;
  height: 250px;
  text-align: center;
  color: #333;
  background: #eee;
}

.center-img{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  width: 100px;
  height: 100px;
  object-fit: cover;
}
</style>

<script>
</script>
</script>


## 水平垂直居中 flex

!> CSS3的新属性 flex,采用 flex 弹性布局会方便很多

<vuep template="#center6"></vuep>

<script v-pre type="text/x-template" id="center6">
<template>
  <div class="center-wrapper">
    <img class="center-img" src="http://images.leegeing.cn/hexoImg/demo.jpeg"/>
  </div>
</template>
<style>
.center-wrapper{
  display: flex;
  /* 垂直居中 */
  align-items:center;
  /* 水平居中 */
  justify-content: center;
  position: relative;
  width: 100%;
  height: 250px;
  text-align: center;
  color: #333;
  background: #eee;
}

.center-img{
  width: 100px;
  height: 100px;
  object-fit: cover;
}
</style>

<script>
</script>
</script>
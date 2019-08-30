# 彩色阴影

!> 通过filter:blur() brightness() opacity()模拟阴影效果

<vuep template="#example"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
  <div class="avatar-shadow"></div>
</template>
<style>
.avatar-shadow {
  position: relative;
  border-radius: 100%;
  width: 80px;
  height: 80px;
  background: url('http://images.leegeing.cn/hexoImg/demo.jpeg') no-repeat center/cover;
}
.avatar-shadow::after {
  position: absolute;
  left: 0;
  top: 10%;
  z-index: -1;
  border-radius: 100%;
  width: 100%;
  height: 100%;
  background: inherit;
  filter: blur(10px) brightness(80%) opacity(.8);
  content: "";
  transform: scale(.95);
}
</style>
<script>
</script>
</script>
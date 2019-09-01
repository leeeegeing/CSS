# 悬停边框变色

<vuep template="#bgHover"></vuep>

<script v-pre type="text/x-template" id="bgHover">
<template>
  <div class="button-wrapper">
    <div class="button__content">悬停边框变色</div>
  </div>  
</template>
<style>
.button-wrapper{
  width:200px;
  height:60px;
  position: relative;
  background: #fff;
  margin:30px auto;
  box-sizing: border-box;
  cursor: pointer;
  text-align: center;
  line-height: 60px;
}
.button-wrapper .button__content{
  height:100%;
  width:100%;
  position: absolute;
  left:0;top:0;
  z-index: 1;
  background: #fff;
}
.button-wrapper::before{
  content:'';
  width:0;
  height:0;
  background:  #00adb5;
  position: absolute;
  top:-1px;right:-1px;
  z-index: 0;
  transition: width .5s,height .5s;
}
.button-wrapper::after{
  content:'';
  width:0;
  height:0;
  background:  #00adb5;
  position: absolute;
  bottom:-1px;left:-1px;
  z-index: 0;
  transition: width .5s,height .5s;
}
.button-wrapper:hover::before{
  width:calc(100% + 2px);
  height:calc(100% + 2px);
}
.button-wrapper:hover::after{
  width:calc(100% + 2px);
  height:calc(100% + 2px);
}
</style>
<script>
</script>
</script>
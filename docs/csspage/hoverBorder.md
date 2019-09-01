# 悬停边框变色

<vuep template="#bgHover"></vuep>

<script v-pre type="text/x-template" id="bgHover">
<template>
  <div class="button__content">
    <div class="button_main">hover me to change</div>
 </div>
</template>
<style lang="Scss">
.btn_container{
  padding:10px;
}
.button_main{
  height:100%;
  width:100%;
  position: absolute;
  left:0;top:0;
  z-index: 1;
  background: #fff;
}
.button_main{
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
.button_main::before{
  content:'';
  width:0;
  height:0;
  background:  #00adb5;
  position: absolute;
  top:-1px;
  right:-1px;
  z-index: 0;
  transition: width .5s,height .5s;
}
.button_main::after{
  content:'';
  width:0;
  height:0;
  background:  #00adb5;
  position: absolute;
  bottom:-1px;
  left:-1px;
  z-index: 0;
  transition: width .5s,height .5s;
}
.button_main:hover::before{
  width:calc(100% + 2px);
  height:calc(100% + 2px);
}
.button_main:hover::after{
  width:calc(100% + 2px);
  height:calc(100% + 2px);
}
</style>
<script>
</script>
</script>
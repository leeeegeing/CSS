# 边框内圆角

!> 背景知识: `box-shadow` ，`outline` ，“多重边框”

<vuep template="#border"></vuep>

<script v-pre type="text/x-template" id="border">
<template>
  <div class="wrapper">
    <p>从前有座山，山上有一个破庙，有一天，一个小和尚他来到庙里,看见庙里的水缸没水了，就挑来水倒满了水缸，还给观音瓶子里加满了水，干枯的杨枝终于恢复了生机。他每天挑水、念经、敲木鱼，夜里不让老鼠来偷东西，生活过得安稳自在。</p>
  </div>
</template>

<style>
  .wrapper{
    padding: 10px;
    background: tan;
    border-radius: 10px;
    box-shadow: 0 0 0 10px #655;
    outline: 10px solid #655;
  }
</style>

<script></script>
</script>
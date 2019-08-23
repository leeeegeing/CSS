
## 单行文本溢出隐藏

<vuep template="#textHien"></vuep>

<script v-pre type="text/x-template" id="textHien">
<template>
  <div class="text-hien">
    从前有座山，山上有一个破庙，有一天，一个小和尚他来到庙里,看见庙里的水缸没水了，就挑来水倒满了水缸，还给观音瓶子里加满了水，干枯的杨枝终于恢复了生机。他每天挑水、念经、敲木鱼，夜里不让老鼠来偷东西，生活过得安稳自在。
  </div>
</template>

<style>
  .text-hien{
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
</style>

<script></script>
</script>


## 多行文本溢出隐藏

!>  适用于 `webkit` 内核的浏览器以及绝大多数的移动设备

<vuep template="#textHien2"></vuep>

<script v-pre type="text/x-template" id="textHien2">
<template>
  <div class="text-hien">
    从前有座山，山上有一个破庙，有一天，一个小和尚他来到庙里,看见庙里的水缸没水了，就挑来水倒满了水缸，还给观音瓶子里加满了水，干枯的杨枝终于恢复了生机。他每天挑水、念经、敲木鱼，夜里不让老鼠来偷东西，生活过得安稳自在。
    不久，来了个高和尚。他渴极了，他一到庙里，就把半缸水喝光了。小和尚让他去挑水，高和尚心想一个人去挑水太吃亏了 ，他要小和尚和他一起去抬水。于是两个人抬着一只水桶去山下取水，抬水的时候水桶必须放在扁担的中央，要不不在中间，两个人就推来推去，谁都不想多出一点 力气。
  </div>
</template>

<style>
  .text-hien{
    overflow : hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
  }
</style>

<script></script>
</script>
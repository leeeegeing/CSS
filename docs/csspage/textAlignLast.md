# 两端对齐

!> 使用 `text-align-last` 对齐两端文本

<vuep template="#textAlignLast"></vuep>

<script v-pre type="text/x-template" id="textAlignLast">

<template>
<div>
  <ul class="justify-text">
    <li class="justify-text-item">账号</li>
    <li class="justify-text-item">密码</li>
    <li class="justify-text-item">电子邮件</li>
    <li class="justify-text-item">通讯地址</li>
  </ul>
</div>
</template>

<style>
ul, li{
  margin: 0;
  padding: 0;
}
li{
  list-style: none;
}
.justify-text-item {
  margin-top: 5px;
  padding: 0 20px;
  width: 100px;
  height: 40px;
  background-color: #42b983;
  line-height: 40px;
  text-align-last: justify; /*核心代码*/
  color: #fff;
}
</style>

<script>
</script>
</script>
# selection 高亮选择

!>  使用 `:selection` 选择器自定义文本选区的高亮样式

<vuep template="#example"></vuep>

<script v-pre type="text/x-template" id="example">
<template>
  <div class="selection-highlight">这是一段文字，尝试按住鼠标进行拖拽选择文字</div>
</template>
<style>
  .selection-highlight::selection {
    background: #ce3d3a;
    color: #fff;
  }
</style>
<script>
</script>
</script>
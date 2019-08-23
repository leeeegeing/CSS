# 立体按钮

!>  通过 `:active` 这个伪类选择器让按钮的点击变得更加立体

<vuep template="#bnutton"></vuep>

<script v-pre type="text/x-template" id="bnutton">
<template>
  <div>
    <button class="button">Button</button>
  </div>
</template>
<style>
.button{
  padding: 10px 20px;
  color: #fff;
  font-size: 16px;
  outline: none;
  border: none;
  border-radius: 5px;
  text-shadow: 0 1px 1px grey;
  box-shadow: 0 8px 0 #068494, 0 8px 4px grey;
  background: linear-gradient(#3de5fb, #26acbd);
}
.button:active{
  box-shadow: 0 4px 0 #068494, 0 4px 2px grey;
  transform: translate(0, 5px)
}
</style>

<script>
</script>

</script>

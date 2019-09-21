# BFC 的基本概念

?> BFC 为 Block Formatting Context 的简写，简称为“块级格式化上下文”

在 BFC 中，盒子从包含块的顶端开始**垂直**地一个接一个地排列，两个盒子之间的垂直的间隙是由他们的 `margin` 值所决定的。**两个相邻的块级盒子的垂直外边距会发生叠加**。

如果一个元素符合触发 BFC 的条件，则 BFC 中的元素布局不受外部影响。

**浮动元素会创建 BFC**，则浮动元素内部子元素主要受该浮动元素影响，所以**两个浮动元素之间是互不影响**的。


### 什么情况下会发生边距叠加呢？

- 父子外边距叠加

- 兄弟外边距叠加



### 他们的共同点是：

- 都属于普通流的块级盒子且参与到相同的块级格式上下文中

- 没有被padding、border、clear和line box分隔开

- 都属于垂直毗邻 *(毗邻意思是边界接壤的意思)* 盒子边缘
  - 盒子的 `top margin` 和它第一个普通流子元素的 `top margin`
  - 盒子的 `bottom margin` 和它下一个普通流兄弟的 `top margin`
  - 盒子的 `bottom margin` 和它父元素的 `bottom margin`
  - 盒子的 `top margin` 和 `bottom margin` ，且没有创建一个新的块级格式上下文，且有被计算为0的`min-height `，被计算为 0 或 auto 的 `height`，且没有普通流子元素


见如下例子：

<vuep template="#BFCMain"></vuep>

<script v-pre type="text/x-template" id="BFCMain">
<template>
  <div>
    <button @click="handleBFC">{{msg}}</button>

    <section class="parent-wrapper" :style="{ overflow: value}">
      <article class="parent-content">
        父子外边距叠加
      </article>
    </section>

    <section class="brother-wrapper" :style="{ overflow: value}">
      <article class="brother-content">兄弟外边距叠加</article>
      <article class="brother-content">兄弟外边距叠加</article>
    </section>
  </div>
  
</template>

<style>
  .parent-wrapper, .brother-wrapper{
    background: #4CAF50;
  }
  .parent-content, .brother-content{
    margin: 10px 0;
    height: 100px;
    background: #FFEB3B;
  }
  .brother-wrapper{
    margin-top: 20px;
  }
</style>

<script>
module.exports = {
  data () {
    return {
      value: '',
      msg: '点我开启BFC'
    }
  },
  methods: {
    // 重置事件
    handleBFC () {
      this.value = this.value === ''? 'hidden': ''
      this.msg = this.msg === '点我开启BFC'? '点我关闭BFC' : '点我开启BFC'
    }
  }
}
</script>
</script>


### BFC 的原理

- 浮动元素不会与任何元素发生叠加，也包括它的子元素
  
- 创建了 BFC 的元素不会和它的子元素发生外边距叠加，一般可以用来清除浮动布局 

- 绝对定位元素和其他任何元素之间不发生外边距叠加，也包括它的子元素

- 计算 BFC 高度的时候，浮动元素也会参与计算


### 如何创建 BFC

创建 BFC 块，需要满足一下几点:

- `float` 的值不为 `none`。

- `overflow` 的值为 `auto`, `scroll`或 `hidden`。

- `display` 的值为 `table-cell`, `table-caption`, `inline-block`中的任何一个。

- `position` 的值不为 `relative` 和 `static` 。


### BFC 的使用场景

?> 外边距折叠（Margin collapsing）只会发生在属于同一BFC的块级元素之间。如果它们属于不同的 BFC，它们之间的外边距则不会折叠。

- 包含浮动元素（清除浮动）

- 导致外边距折叠 / 防止外边距折叠

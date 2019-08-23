# 图片防抖

**起因**

在项目中经常会遇到加载图片过慢，导致 `DOM` 元素没有被图片撑开造成 DOM 塌陷，后续等图片加载完成后，页面会造 `DOM` 的高度变化，进而产生视觉上面的抖动效果.

**解决**
将 `DOM` 元素的宽高比例设为和图片的比例一致，即便图片没有加载成功，也不会造成 DOM 的塌陷。


!>  `padding-top` 和 `width 100%` 的比例决定了图片的宽高比

<vuep template="#imgAntiShake"></vuep>

<script v-pre type="text/x-template" id="imgAntiShake">
<template>
  <div>
    <div class="wrapper-flex"> 
      <div class="wrapper-item"> 
        <div>图片未防抖</div>
        <div class="img-shake-default">
          <img :src="imgUrl"/>
        </div>
      </div>
      <div class="wrapper-item">
        <div>图片防抖</div>
        <div class="img-shake">
          <img v-bind:src="imgUrl"/>
        </div>
      </div>
    </div>
    <div class="button-wrapper"><button class="button" @click="handleImg">重置图片</button></div>
  </div>
</template>

<style>

.wrapper-flex{
  display: flex;
  width: 80%;
}
.wrapper-item{
  padding: 10px;
  width: 50%;
  flex: 1;
}
.wrapper-item img{
  width: 100%;
  height: 100%;
}
.img-shake-default{
  max-height: 271px;
  overflow: hidden;
}
.img-shake{
  position: relative;
  padding-top: 100%; /*核心代码*/
  background: #eee;
  overflow: hidden;
}
.img-shake img{
  position: absolute;
  top: 0;
  left: 0;
  object-fit: cover;
}
</style>

<script>
module.exports = {
  data () {
    return {
      imgUrl: 'http://images.leegeing.cn/hexoImg/demo.jpeg',
      isClick: true
    }
  },
  methods: {
    // 重置事件
    handleImg () {
      this.imgUrl = ''
      if(this.isClick) {
        console.log('click me')
        // 防止用户重复点击
        this.isClick = false
        // 模拟加载图片所需要的时间
        setTimeout(() => {
          this.imgUrl = 'http://images.leegeing.cn/hexoImg/demo.jpeg'
          this.isClick = true
        },2000)
      }
    }
  }
}
</script>
</script>

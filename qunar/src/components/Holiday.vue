<template>
  <div class="holiday">
    <div class="title">假期攻略</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key='item.id'>
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="img">
        </div>
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeHoliday',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/mixins.styl'
  .title
    line-height .8rem
    background #eee
    text-indent .2rem
    font-size 0.3rem
    font-weight bold
  .item-img-wrapper
    height 0
    padding-bottom 37%
    background #ccc
    overflow hidden
    .item-img
      width 100%
  .item-info
    flex 1
    padding .1rem
    min-width 0
    .item-title
      line-height .5rem
      font-size .29rem
      ellipsis()
    .item-desc
      line-height .5rem
      color #ccc
      ellipsis()
</style>

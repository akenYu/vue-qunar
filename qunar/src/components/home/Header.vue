<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xeb99;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xeb9c;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{ this.city}}
        <span class="iconfont arrow-icon">&#xe62a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  },
}
</script>

<style scoped lang="stylus">
  @import '~@/assets/styles/varibles.styl'
  .header
    height .86rem
    display flex
    background $bgcolor
    color #fff
    .header-left
      width .64rem
      float left
      margin-top .24rem
      .back-icon
        text-align center
        font-size .4rem
    .header-input
      flex 1
      height .64rem
      line-height .64rem
      margin .12rem 0 0 .2rem
      padding-left .2rem
      background #fff
      border-radius .1rem
      color #ccc
    .header-right
      min-width 1.04rem
      padding 0 .1rem
      float right
      text-align center
      margin-top .28rem
      color white
      .arrow-icon
        font-size .24rem
</style>

<template>
  <div class="header">
    <router-link
      tag="div" 
      to='/' 
      class="header-back"
      v-show="showBack"
    >
      <span class="iconfont header-abs-back">&#xeb99;</span>
    </router-link>
    <div 
      class="header-fixed"
      v-show="!showBack"
      :style="opacityStyle"  
    >
      <router-link tag="div" to='/'>
        <span class="iconfont header-fixed-back">&#xeb99;</span>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data() {
    return {
      showBack: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll() {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showBack = false
      } else {
        this.showBack = true
      }
    }
  },
  activated() {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated() {
    window.removeEventListener('scroll', this.handleScroll)
  },
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header-back
    position absolute
    left .2rem
    top .2rem
    width .8rem
    height .8rem
    line-height .8rem
    text-align center
    border-radius .4rem
    background rgba(0, 188, 212, .5)
    .header-abs-back
      color #fff
      font-size .4rem
  .header-fixed
    z-index 2
    position fixed
    top 0
    right 0
    left 0
    height .86rem
    line-height .86rem
    text-align center
    color #fff
    background $bgcolor
    font-size .32rem
    .header-fixed-back
      position absolute
      top 0
      left 0
      width .64rem
      font-size .4rem
      color #fff
</style>

<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p57/201211/08/c42f2e7088a8a11093835fbb.jpg_600x330_fcee2d2d.jpg" alt="img">
      <div class="banner-info">
        <div class="banner-title">
          漓江(AAAAA景区)
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe75d;</span>
          26
        </div>
      </div>
    </div>
    <detail-gallary 
      :imgs="imgs"
      v-show="showGallary"
      @close="handleBannerClose"
    />
  </div>
</template>

<script>
import DetailGallary from './Gallary'
export default {
  name: 'DetailBanner',
  data() {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p57/201211/08/c42f2e7088a8a11093835fbb.jpg_600x330_fcee2d2d.jpg',
             'http://img1.qunarzz.com/sight/p0/201405/27/6f3e880957993c658adc1226fae21719.jpg_r_800x800_9c14ed0d.jpg']
    }
  },
  methods: {
    handleBannerClick() {
      this.showGallary = true
    },
    handleBannerClose() {
      this.showGallary = false
    }
  },
  components: {
    DetailGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    overflow hidden
    position relative
    height 0
    padding-bottom 55%
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      color #fff
      background-image linear-gradient(to bottom, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-title
        flex 1
        padding 0 .2rem
        font-size .36rem
        text-shadow rgba(0, 0, 0, 0.7) 0px 1px 2px
        color #ddd
      .banner-number
        padding 0 .4rem
        margin-top .1rem
        height .4rem
        width .6rem
        line-height .4rem
        border-radius .2rem
        background rgba(0, 0, 0, .6)
        font-size .24rem
        .banner-icon
          font-size .26rem
</style>

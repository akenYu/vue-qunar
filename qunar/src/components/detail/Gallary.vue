<template>
  <div class="gallary" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(item, index) in imgs" :key="index">
          <img class="gallary-img" :src="item" alt="img">
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailGallary',
  props: {
    imgs: Array
  },
  data() {
    return {
      swiperOptions: {
        pagination: {
          el: '.swiper-pagination',
          type: 'fraction'
        },
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    handleGallaryClick() {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .gallary >>> .swiper-container
    overflow inherit
  .gallary
    display flex
    flex-direction column
    justify-content center
    z-index 2
    position fixed
    left 0
    right 0
    top 0
    bottom 0
    background #000
    .gallary-img
      height 100%
      width 100%
    .swiper-pagination
      color #fff
      bottom -4rem


</style>


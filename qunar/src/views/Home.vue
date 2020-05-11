<template>
  <div class="home">
    <home-header/>
    <home-swiper/>
    <home-icons/>
    <home-recommend/>
    <home-holiday/>
  </div>
</template>

<script>
import HomeHeader from '../components/Header'
import HomeSwiper from '../components/Swiper'
import HomeIcons from '../components/Icons'
import HomeRecommend from '../components/Recommend'
import HomeHoliday from '../components/Holiday'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeHoliday
  }
}
</script>

<style>
  
</style>
<template>
  <div class="home">
    <home-header :city="city" />
    <home-swiper :list="swiperList" />
    <home-icons :list="iconList" />
    <home-recommend :list="recommendList" />
    <home-holiday :list="holidayList" />
  </div>
</template>

<script>
import HomeHeader from '../components/home/Header'
import HomeSwiper from '../components/home/Swiper'
import HomeIcons from '../components/home/Icons'
import HomeRecommend from '../components/home/Recommend'
import HomeHoliday from '../components/home/Holiday'
import axios from 'axios'

export default {
  name: 'Home',
  data() {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      holidayList: []
    }
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeHoliday
  },
  methods: {
    getHomeInfo() {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res) {
      res = res.data
      if (res.ret) {
        let data = res.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.holidayList = data.holidayList

      }
    }
  },
  mounted() {
    this.getHomeInfo()
  },
}
</script>

<style>
  
</style>
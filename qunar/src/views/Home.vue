<template>
  <div class="home">
    <home-header />
    <home-swiper :list="swiperList" />
    <home-icons :list="iconList" />
    <home-recommend :list="recommendList" />
    <home-holiday :list="holidayList" />
  </div>
</template>

<script>
import axios from 'axios'
import { mapState } from 'vuex'
import HomeHeader from '../components/home/Header'
import HomeSwiper from '../components/home/Swiper'
import HomeIcons from '../components/home/Icons'
import HomeRecommend from '../components/home/Recommend'
import HomeHoliday from '../components/home/Holiday'

export default {
  name: 'Home',
  data() {
    return {
      currentCity: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      holidayList: []
    }
  },
  computed: {
    ...mapState(['city'])
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
      axios.get('/api/index.json?city=' + this.city)
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res) {
      res = res.data
      if (res.ret) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.holidayList = data.holidayList
      }
    }
  },
  mounted() {
    this.currentCity = this.city
    this.getHomeInfo()
  },
  activated() {
    if (this.currentCity !== this.city) {
      this.currentCity = this.city
      this.getHomeInfo()
    }
  },
}
</script>

<style>
  
</style>
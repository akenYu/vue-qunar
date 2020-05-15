<template>
  <div class="detail">
    <detail-banner
      :sightname="sightName"
      :bannerimg="bannerImg"
      :gallaryimgs="gallaryImgs"
    />
    <detail-header />
    <detail-list
      :categorylist="categoryList"
    />
    <div class="content"></div>
  </div>
</template>

<script>
import axios from 'axios'
import DetailBanner from '../components/detail/Banner'
import DetailHeader from '../components/detail/Header'
import DetailList from '../components/detail/List'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data() {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      categoryList: [],
    }
  },
  methods: {
    getDetailInfo() {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetDateSucc)
    },
    handleGetDateSucc(res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.categoryList = data.categoryList
      }
    }
  },
  mounted() {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height 20rem
</style>

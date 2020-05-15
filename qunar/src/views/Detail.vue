<template>
  <div class="detail">
    <detail-banner />
    <detail-header />
    <detail-list :list="list" />
    <div class="content"></div>
  </div>
</template>

<script>
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
      list: [
        { 
          title: '成人票',
          children: [{
            title: '成人票一号馆',
            children: [{
              title: '成人票一号馆 - 售票厅'
            }]
          }, {
            title: '成人票二号馆'
          }]
        },
        { title: '学生票' },
        { title: '儿童票' },
        { title: '特惠票' },
      ]
    }
  },
}
</script>

<style lang="stylus" scoped>
  .content
    height 50rem
</style>

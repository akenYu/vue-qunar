<template>
  <div class="holiday">
    <div class="title">假期攻略</div>
    <ul>
      <li class="item border-bottom" v-for="item of holidayList" :key='item.id'>
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
    data() {
      return {
        holidayList: [
          {
            id: '01',
            imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
            title: '清远周边逛',
            desc: '人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
          },
          {
            id: '02',
            imgUrl: 'http://img1.qunarzz.com/sight/source/1811/b8/5d599bbdcf8b57.jpg_r_640x214_2ee055e3.jpg',
            title: '浮在海上的绿洲',
            desc: '南国滨海之城，避寒胜地，有暖暖的阳光，海风习习，吃着海鲜逛逛老街多惬意啊'
          },
          {
            id: '03',
            imgUrl: 'http://img1.qunarzz.com/sight/source/1811/f8/29dfa785277839.jpg_r_640x214_7d051523.jpg',
            title: '阳江温泉知多少',
            desc: '这里的天空和大海让人心旷神怡，配上舒缓的优美音乐，泡个暖暖的温泉岂不美哉'
          },
          {
            id: '04',
            imgUrl: 'http://img1.qunarzz.com/sight/source/1507/d9/2ddc7652fdba16.jpg_r_640x214_5e62f1a3.jpg',
            title: '深圳周边游',
            desc: '远离城市拥堵，去周边开启清新假期吧。'
          },
        ]
      }
    },
  }
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/mixins.styl'
  .title
    margin-top .2rem
    line-height .8rem
    background #eee
    text-indent .2rem
    font-size 0.3rem
    font-weight bold
  .item-img-wrapper
    height 0
    padding-bottom 35%
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

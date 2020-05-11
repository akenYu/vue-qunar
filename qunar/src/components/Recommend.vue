<template>
  <div class="recommend">
    <div class="recomend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key='item.id'>
        <img class="item-img" :src="item.imgUrl" alt="img">
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'HomeRecommend',
    data() {
      return {
        recommendList: [
          {
            id: '01',
            imgUrl: 'https://imgs.qunarzz.com/sight/p0/2005/39/392f70c14ff4bdaba3.img.jpg_256x144_8d8a790f.jpg',
            title: '长隆野生动物世界',
            desc: '熊猫三胞胎，神奇动物夜，与您共享欢乐时光'
          },
          {
            id: '02',
            imgUrl: 'https://imgs.qunarzz.com/sight/p0/1509/80/9535a0d28468b3c6c910d87f1a4fdbe8.water.jpg_256x144_9444daaa.jpg',
            title: '岭南印象园',
            desc: '岭南印象园江面上龙船竞渡，水中好戏不断'
          },
          {
            id: '03',
            imgUrl: 'https://imgs.qunarzz.com/sight/p0/1603/ee/ee3013caaa28ae7490.water.jpg_256x144_4e91a0fa.jpg',
            title: '增城白水寨风景名胜区',
            desc: '北回归线上的瑰丽翡翠'
          },
          {
            id: '04',
            imgUrl: 'https://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_256x160_ca478972.jpg',
            title: '深圳野生动物园',
            desc: '放养式动物园让你和动物们“零距离”'
          },
        ]
      }
    },
  }
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/mixins.styl'
  .recomend-title
    margin-top .2rem
    line-height .8rem
    background #eee
    text-indent .2rem
    font-size 0.3rem
    font-weight bold
  .item
    overflow hidden
    display flex
    height 1.9rem
    padding-right 0.1rem
    .item-img
      height 1.7rem
      width 3rem
      padding .1rem
      border-radius 8%
    .item-info
      flex: 1
      margin-top .1rem
      paddding 1
      min-width 0
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
      .item-button
        line-height .44rem
        margin-top .16rem
        background #ff9300
        padding 0 .2rem
        border-radius .06rem
        color: #fff
</style>

<template>
  <div class="list">
    <li class="item"
        v-for="item of letters"
        :key="item"
        :ref="item"
        @click="handleLetterClick"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
    >
      {{ item }}
    </li>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data() {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated() {
    // 获取A字母到顶部的距离
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters() {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleLetterClick(e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart() {
      this.touchStatus = true
    },
    handleTouchMove(e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          // 获取滑动时到A字母的距离
          const touchY = e.touches[0].clientY - 109
          // 获取触发的时哪个字母 先算出两者的差值 再除以每个字母的高度 
          const index = Math.floor((touchY - this.startY) / 20) + 2
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 5)
      }
    },
    handleTouchEnd() {
      this.touchStatus = false
    }
  },
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .list
    display flex
    flex-direction column
    justify-content center
    position absolute
    top 1.58rem
    right 0
    bottom 0
    width .4rem
    .item
      text-align center
      list-style none
      line-height .4rem
      color $bgcolor
</style>

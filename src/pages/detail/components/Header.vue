<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <span class="iconfont header-abs-back">&#xe624;</span>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStle">
      <router-link to="/">
        <span class="iconfont header-fixed-back">&#xe624;</span>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStle: 0
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header-abs
    position absolute
    left .2rem
    top .2rem
    width .8rem
    height .8rem
    line-height .8rem
    border-radius .4rem
    background rgba(0, 0, 0, .8)
    text-align center
    .header-abs-back
      color #fff
      font-size .4rem
  .header-fixed
    height $headerHeight
    line-height $headerHeight
    overflow hidden
    text-align center
    color #fff
    background-color $bgColor
    font-size .32rem
    position fixed
    top 0
    left 0
    right 0
    .header-fixed-back
      position absolute
      top 0
      left 0
      width 0.64rem
      text-align center
      font-size .4rem
      color #fff
</style>

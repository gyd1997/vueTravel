<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img src="//img1.qunarzz.com/sight/p0/1602/53/53cf6caed9f9b9ee90.img.jpg_600x330_ddcee9e0.jpg" class="banner-img">
      <div class="banner-info">
        <div class="banner-title">华清宫(AAAAA景区)</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>43
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from '../../../common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1602/de/de8400021b664c5390.img.jpg_r_800x800_980118e2.jpg', '//img1.qunarzz.com/sight/p0/1602/53/53cf6caed9f9b9ee90.img.jpg_600x330_ddcee9e0.jpg', 'http://img1.qunarzz.com/sight/p0/1602/e2/e2f5318eb8279a3190.img.jpg_r_800x800_91522868.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      color #fff
      background-image linear-gradient(to top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
      .banner-title
        flex 1
        font-size .32rem
        padding 0 .2rem
      .banner-number
        margin-top .14rem
        padding 0 .4rem
        height .32rem
        line-height .32rem
        border-radius .2rem
        background rgba(0, 0, 0, .8)
        font-size .24rem
        .banner-icon
          font-size .24rem
</style>

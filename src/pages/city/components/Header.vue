<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div>
        <div class="iconfont header-back">&#xe624;</div>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header
    height $headerHeight
    line-height $headerHeight
    overflow hidden
    text-align center
    color #fff
    background-color $bgColor
    font-size .32rem
    position relative
    .header-back
      position absolute
      top 0
      left 0
      width 0.64rem
      text-align center
      font-size .4rem
      color #fff
</style>

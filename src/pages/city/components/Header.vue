<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont city-back">&#xe624;</div>
    </router-link>
    城市选择
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
    position relative
    overflow hidden
    height $headerHeight
    line-height $headerHeight
    text-align center
    color #fff
    font-size .32rem
    background-color $bgColor
    .city-back
      width .64rem
      top 0
      left 0
      position absolute
      text-align center
      font-size .4rem
      color #fff
</style>

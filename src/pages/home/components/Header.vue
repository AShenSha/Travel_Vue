<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont icon-back">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.$store.state.city}}
        <span class="iconfont">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader'
}
</script>
<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
    .header
      display: flex
      height: $headerHeight
      line-height : $headerHeight
      background-color : $bgColor
      color: #fff
      .header-left
        width: .64rem
        float: left
        .icon-back
          text-align: center
          font-size : .4rem
      .header-input
        flex: 1
        height : .62rem
        background : #fff
        border-radius : .1rem
        margin-top : .12rem
        margin-left : .2rem
        color:#ccc
        line-height .62rem
        padding-left:.1rem
      .header-right
        min-width: 1.04rem
        margin-left .1rem
        float: left
        text-align :  center
        color :#fff
</style>

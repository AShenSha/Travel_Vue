<template>
  <div>
    <router-link to="/" tag="div" v-show="showAbs" class="header-abs">
      <div class="iconfont icon-abs-back">&#xe624;</div>
    </router-link>
    <div class="header-fixed" :style="opacityStyle" v-show="!showAbs">
      景点详情
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opactiy: 0
      }
    }
  },
  methods: {
    handleScroll () {
      // console.log('scroll')
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>
<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header-abs
    position absolute
    left .2rem
    top .2rem
    height .6rem
    width .6rem
    border-radius .4rem
    background rgba(0,0,0,.8)
    .icon-abs-back
      color #ffffff
      font-size .4rem
      padding .08rem
  .header-fixed
    position fixed
    overflow hidden
    top 0
    left 0
    right 0
    height $headerHeight
    line-height $headerHeight
    text-align center
    color #fff
    font-size .32rem
    background-color $bgColor
    .header-fixed-back
      width .64rem
      top 0
      left 0
      position absolute
      text-align center
      font-size .4rem
      color #fff
</style>

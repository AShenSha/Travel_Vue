<template>
  <div class="container" @click="handelGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item, index) of imgs" :key="index">
          <img class="gallary-img" :src="item"/>
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CommonGallay',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  methods: {
    handelGallaryClick () {
      this.$emit('close')
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow inherit
  .container
    display flex
    flex-direction column
    justify-content center
    position fixed
    z-index 99
    left 0
    right 0
    top 0
    bottom 0
    background #000
    .wrapper
      // height 0
      // width 100%
      // padding-bottom 55%
      background #fff
      .gallary-img
        width 100%
      .swiper-pagination
        color #fff
        bottom -1rem
</style>

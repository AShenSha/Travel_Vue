<template>
  <div>
    <div class="title">
      热销推荐
    </div>
    <ul>
      <router-link tag="li" :to="'/detail/' + item.id" class="item border-bottom" v-for="item of list" :key='item.id'>
          <img class="item-img" :src="item.imgUrl" >
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>
<style lang="stylus" scoped>
  @import '~@/assets/styles/mixins.styl'
  .title
    background-color :#eee
    line-height  :.8rem
    margin-top :.2rem
    text-indent :.2rem
  .item
    display:flex
    height :1.9rem
    overflow :hidden
    .item-img
      height :1.7rem
      width :1.7rem
      padding:.1rem
    .item-info
      flex :1
      padding:.1rem
      min-width :0
      .item-title
        line-height :.54rem
        font-size :.32rem
        ellipsis()
      .item-desc
        line-height :.4rem
        color:#ccc
        ellipsis()
      .item-button
        line-height :.44rem
        margin-top :.16rem
        background-color :#ff9300
        border-radius :.06rem
        padding 0 .1rem
        color :#fff
</style>

<template>
<div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
    <!-- slides -->
    <swiper-slide  v-for="item of list" :key="item.id"><img :src="item.imgUrl"/></swiper-slide>
    <div class="swiper-pagination" slot="pagination"> </div>
  </swiper>
</div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
      // swiperList: [{
      //   id: '0001',
      //   imgUrl: '//img1.qunarzz.com/vc/34/71/86/e7cbde10e4094dc88bcf351bf0.jpg'
      // }, {
      //   id: '0002',
      //   imgUrl: '//img1.qunarzz.com/vc/32/0e/3b/e245f95d37fe21d8b870ad87af.jpg'
      // }]
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }

  }
}

</script>
<style lang="stylus" scoped>
.wrapper>>> .swiper-pagination-bullet-active
    background:#fff !important
.wrapper
  width:100%
  height:0
  overflow:hidden
  padding-bottom:30.5%
  background:#ccc
  .wrapper-img
    width:100%
</style>b

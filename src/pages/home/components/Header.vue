<template>
<div class="header">
  <div class="header-left"><div class="iconfont back-icon">&#xe624;</div></div>
  <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市/地点/主题</div>
  <router-link to="/city">
  <div class="header-right">{{city}}<span class="iconfont arrow-icon">&#xe64a;</span></div>
  </router-link>
</div>
</template>
<script>
import {mapState, mapGetters} from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city']),
    ...mapGetters(['doubleCity'])
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  font-size:12px
  display:flex
  line-height:$headerHeight
  background: $bgColor
  color:#fff
.header-left
  height:.64rem
  float:left
  .back-icon
    text-align: center
    font-size:.4rem
.header-input
  flex:1
  margin-top:.12rem
  margin-left:.2rem
  height:.64rem
  padding-left:.2rem
  line-height:.64rem
  background:#fff
  color:#ccc
  border-radius:.1rem
.header-right
  width:1.24rem
  float:right
  text-align:center
  color:#fff
  .arrow-icon
    font-size:.24rem
</style>

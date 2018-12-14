<template>
<div class="header">
城市选择
<router-link to="/">
<div class="header-left"><div class="iconfont header-back">&#xe624;</div></div>
</router-link>
</div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
.header
  position:relative
  font-size:12px
  line-height:$headerHeight
  background: $bgColor
  color:#fff
  text-align:center
  .header-back
    font-size:.4rem
    width:.64rem
    position:absolute
    top:0
    left:0
    color:#fff
</style>

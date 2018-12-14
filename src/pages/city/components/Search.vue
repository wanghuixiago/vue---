<template>
<div>
<div class="search">
<input v-model="keyword" type="text" placeholder="输入城市名或拼音" class="search-input"/>
</div>
      <div class="search-content"
         ref="search"
         v-show="keyword"
         >
      <ul>
         <li class="search-item"
         :key="item.id"
         v-for="item of list"
         @click="handleCityClick(item.name)"
         >
           {{item.name}}
         </li>
         <li class="search-item" v-show="hasNoData">
           没有找到匹配数据
         </li>
      </ul>
      </div>
</div>
</template>
<script>
import {mapMutations} from 'vuex'
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in (this.cities)) {
          this.cities[i].forEach(value => {
            if (
              value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1
            ) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.search {
  height: 0.72rem;
  padding: 0 0.1rem;
  background: $bgColor;
  position: relative;

  .search-input {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 0.62rem;
    line-height: 0.62rem;
    border-radius: 0.06rem;
    text-align: center;
    color: #666;
  }
}

.search-content {
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
  background: #eee;
  z-index: 1;
   .search-item{
     line-height 0.62rem;
     padding-left 0.2rem;
     color:#666;
     background: #fff;
     border-bottom:1px solid #ccc;
     font-size:.32rem
   }
}
</style>

<template>
    <div class="recs">
        <div class="recs-title">周末去哪儿</div>
        <ul>
            <li class="item" v-for="item of list" :key="item.index">
                <div class="item-img-wrapper">
                <img class="item-img" :src="item.imgUrl"/>
                </div>
                <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.recs {
    font-size: 12px;

    .recs-title {
        line-height: 0.8rem;
        background: #eee;
        text-align: center;
    }
    .item-img-wrapper {
        overflow:hidden
        height:0
        padding-bottom:37.09%
        .item-img {
            width: 100%
        }
    }

        .item-info {
            flex: 1;
            padding: 0.1rem;
            min-width: 0;
        }

        .item-title {
            line-height: 0.54rem;
            font-size: 0.32rem;
            ellipsis();
        }

        .item-desc {
            line-height: 0.4rem;

            color:#ccc {
                ellipsis();
            }
        }
    }
</style>

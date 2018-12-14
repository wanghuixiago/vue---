<template>
    <div class="recs">
        <div class="recs-title">热销推荐</div>
        <ul>
            <router-link
            :to="'/detail/'+item.id"
            tag='li'
            class="item"
            v-for="item of list"
            :key="item.index">
                <img class="item-img" :src="item.imgUrl"/>
                <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
                <button class="item-btn">查看详情</button>
                </div>
            </router-link>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'HomeRecs',
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

    .item {
        display: flex;
        height: 1.9rem;
        overflow: hidden;
        border-bottom: 1px solid #ccc;

        .item-img {
            width: 1.7rem;
            height: 1.7rem;
            padding: 0.1rem;
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

        .item-btn {
            font-size: 0.2rem;
            margin-top: 0.2rem;
            background: #ff9300;
            padding: 0.1rem;
            height: 0.44rem;
            border-radius: 0.06rem;
            color: #fff;
        }
    }
}
</style>

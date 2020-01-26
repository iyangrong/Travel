<template>
    <div>
        <h2 class="recommend-sale">热销推荐</h2>
        <ul>
            <li v-for="item in recommendList" :key="item.id">
                <img class="mp-like-img" :src="item.imgUrl" />
                <div class="recommend-main">
                    <div class="title_and_desc">
                        <p class="recommend-title signale">{{item.title}}</p>
                        <p class="recommend-desc signale">{{item.desc}}</p>
                    </div>
                    <div class="price_and_pi">
                        <button class="item-button">查看详情</button>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name: 'HomeRecommend',
    props: {
        recommendList: Array
    },
    data() {
        return {}
    }
}
</script>
<style scoped>
    .recommend-sale {
        height: .8rem;
        line-height: .8rem;
        padding-left: .26rem;
        color: #2e2e2e;
        background-color: #eee;
        margin-top: .2rem;
    }
    li {
        padding: .3rem 0 .3rem .2rem;
        border-bottom: .01rem solid #eee;
        display: flex;
    }
    li:last-child {
        border-bottom: none;
    }
    .mp-like-img {
        width: 2rem;
        height: 2rem;
        margin-right: .2rem;
    }
    .recommend-main {
        display: flex;
        justify-content: space-between;
        flex-direction: column;
        width: calc(100% - 2.2rem);
    }
    .title_and_desc {
        margin-top: 0.1rem;
    }
    .price_and_pi {
        margin-bottom: 0.1rem;
    }
    .signale {
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        width: 100%;
    }
    .recommend-title {
        color: #2e2e2e;
        font-size: .32rem;
        font-weight: bold;
        margin-bottom: .1rem;
    }
    .recommend-desc {
        color: #c7c7c7;
    }
    .recommend-price {
        color: #df9b68;
        font-size: .32rem;
    }
    .recommend-pi {
        color: #c7c7c7;
        margin-right: 1.5rem;
    }
    .item-button {
        background-color: #ff9300;
        padding: 0 .2rem;
        border-radius: 0.06rem;
        color: #fff;
        line-height: .44rem;
    }
</style>
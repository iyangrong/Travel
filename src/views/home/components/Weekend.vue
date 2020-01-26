<template>
    <div>
        <h2 class="recommend-sale">周末去哪儿</h2>
        <ul>
            <li v-for="item in weekendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="mp-like-img" :src="item.imgUrl" />
                </div>
                <div class="item-title">
                    <span class="item-title-title signale">{{item.title}}</span>
                    <span class="item-title-desc signale">{{item.desc}}</span>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name: 'HomeWeekend',
    props: {
        weekendList: Array
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
    .item-img-wrapper {
        overflow: hidden;
        height: 0;
        padding-bottom: 33.9%;
    }
    .mp-like-img {
        width: 100%;
    }
    .item-title {
        padding: .14rem .2rem .2rem .2rem;
    }
    .item-title span {
        display: block;
    }
    .item-title-title {
        padding-right: 1.4rem;
        color: #212121;
        font-size: .28rem;
        line-height: .48rem;
    }
    .item-title-desc {
        padding-right: 1.4rem;
        color: #616161;
        font-size: .24rem;
        line-height: .42rem;
    }
    .signale {
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        width: 100%;
    }
</style>
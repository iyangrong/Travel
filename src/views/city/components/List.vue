<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">北京</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrapper" v-for="item of hotCities" :key="item.id">
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div 
                class="area" 
                v-for="(item, key) of cities" 
                :key="key"
                :ref="key"
            >
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div class="item border-bottom" v-for="itemcity of item" :key="itemcity.id">{{itemcity.name}}</div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import BScroll from 'better-scroll'
export default {
    name: 'CityList',
    props: {
        cities: Object,
        hotCities: Array,
        letter: String
    },
    mounted() {
        this.scroll = new BScroll(this.$refs.wrapper)
    },
    watch: {
        letter() {
            const element = this.$refs[this.letter][0]
            this.scroll.scrollToElement(element)
        }
    }
}
</script>
<style scoped>
    .list {
        position: absolute;
        top: 1.58rem;
        left: 0;
        right: 0;
        bottom: 0;
        position: absolute;
        overflow: hidden;
    }
    .title {
        line-height: 0.56rem;
        background-color: #eee;
        padding-left: 0.26rem;
        color: #666;
    }
    .border-topbottom {
        border: #ccc;
    }
    .button-list {
        padding: 0.1rem 0.6rem 0.1rem 0.1rem;
        overflow: hidden;
    }
    .button-wrapper {
        width: 33.33%;
        float: left;
    }
    .button {
        margin: 0.1rem;
        text-align: center;
        border: 0.02rem solid #ccc;
        padding: 0.1rem 0;
        border-radius: 0.06rem;
    }
    .item {
        line-height: 0.76rem;
        color: #666;
        padding-left: 0.2rem;
    }
</style>
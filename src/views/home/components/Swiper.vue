<template>
    <div class="wrapper">
        <swiper :options="swiperOption" v-if="swiperList.length">
            <!-- slides -->
            <swiper-slide v-for="item in swiperList" :key="item.id">
                <img class="swiper-img" :src="item.imgUrl" />
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
export default {
    name: 'HomeSwiper',
    props: {
        swiperList: Array
    },
    data() {
        return {
            swiperOption: {
                pagination: '.swiper-pagination',
                loop: true
            }
        }
    },
    computed: {
        IsShow() {
            return this.swiperList.length
        }
    }
}
</script>
<style scoped>
    .wrapper {
        overflow: hidden;
        width: 100%;
        height: 0;
        padding-bottom: 31.25%;
    }
    .swiper-img {
        width: 100%;
    }
</style>
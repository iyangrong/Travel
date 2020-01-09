<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
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
    data() {
        return {
            swiperOption: {
                pagination: '.swiper-pagination',
                loop: true
            },
            swiperList: [
                {
                    id: '0001',
                    imgUrl: 'https://imgs.qunarzz.com/vs_ceph_vs_tts/ee6aebea-54d1-480d-a2c0-783034a47c7f.jpg_r_390x260x90_02e70f0b.jpg'
                },
                {
                    id: '0002',
                    imgUrl: 'https://imgs.qunarzz.com/vs_ceph_vs_tts/69cb37c9-29f3-4b7e-88ed-91d4a0a0142d.jpg_r_480x320x90_aa082e38.jpg'
                }
            ]
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
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
                    imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20201/8c458e9fe5b5f4575b1d7ec0489a9ff8.jpg_750x200_f0fbf511.jpg'
                },
                {
                    id: '0002',
                    imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20201/9c4bd16baa22bcd6810b714b225b5c33.jpg_750x200_95d6ad38.jpg'
                },
                {
                    id: '0003',
                    imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201912/0b26e9760c2673c63c05e1efce1275ea.jpg_750x200_495c0a72.jpg'
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
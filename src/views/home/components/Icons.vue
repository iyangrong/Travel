<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(list, index) in pages" :key="index">
                <div class="icon" v-for="item in list" :key="item.id">
                    <img :src="item.imgUrl" style="opacity: 1;">
                    <p>{{item.desc}}</p>
                </div>  
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
export default {
    name: 'HomeIcons',
    props: {
        iconList: Array
    },
    data() {
        return {
            swiperOption: {
                pagination: '.swiper-pagination',
                loop: true,
                autoplay: false
            }
        }
    },
    computed: {
        pages() {
            let pages = []
            for(let i = 0; i < this.iconList.length; i++) {
                let m = Math.floor(i / 8)
                if(!pages[m]) {
                    pages[m] = []
                }
                pages[m].push(this.iconList[i])
            }
            console.log('array', pages)
            return pages
        }
    }
}
</script>
<style scoped>
    .icons {
        height: 0;
        padding-bottom: 50%;
        overflow: hidden;
        margin-top: 0.3rem;
    }
    .swiper-container {
        height: 0;
        padding-bottom: 50%;
        overflow: hidden;
    }
    .icon {
        overflow: hidden;
        width: 25%;
        padding-bottom: 25%;
        float: left;
        position: relative;
        box-sizing: border-box;
    }
    .icon img {
        display: block;
        position: absolute;
        top: 0;
        left: 10%;
        width: 80%;
    }
    .icon p {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        text-align: center;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
    }
</style>


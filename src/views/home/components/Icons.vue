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
    data() {
        return {
            swiperOption: {
                pagination: '.swiper-pagination',
                loop: true
            },
            iconList: [
            {
                id: '0001',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                desc: '景点门票'
            },
            {
                id: '0002',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/fc/b10a6b2e4f0fe102.png',
                desc: '万龙滑雪'
            },
            {
                id: '0003',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
                desc: '故宫'
            },
            {
                id: '0004',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/fc/b10a6b2e4f0fe102.png',
                desc: '静之湖滑雪'
            },
            {
                id: '0005',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
                desc: '一日游'
            },
            {
                id: '0006',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
                desc: '古北水镇'
            },
            {
                id: '0007',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/fc/b10a6b2e4f0fe102.png',
                desc: '北京滑雪'
            },
            {
                id: '0008',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
                desc: '颐和园'
            },
            {
                id: '0009',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                desc: '泡温泉'
            },
            {
                id: '0010',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
                desc: '北京必游'
            }
        ]
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


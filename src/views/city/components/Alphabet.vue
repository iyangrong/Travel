<template>
    <ul class='list'>
        <li 
            class="item" 
            v-for="(item, key) of cities" 
            :key="key"
            @touchstart="handleTouchStart"
            @touchmove="handleTouchMove"
            @touchend="handleTouchEnd"
            @click="handleLetterClick"
        >
            {{key}}
        </li>
    </ul>
</template>
<script>
export default {
    name: 'CityAlphabet',
    props: {
        cities: Object
    },
    data() {
        return {
            touchStatus: false
        }
    },
    methods: {
        handleLetterClick(e) {
            this.$emit('change', e.target.innerText)
        },
        handleTouchStart() {
            this.touchStatus = true
        },
        handleTouchMove() {

        },
        handleTouchEnd() {
            this.touchStatus = false
        }
    }
}
</script>
<style scoped>
    .list {
        position: absolute;
        top: 1.58rem;
        right: 0;
        bottom: 0;
        width: 0.4rem;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    .item {
        text-align: center;
        line-height: 0.4rem;
        color: #00bcd4;
    }
</style>
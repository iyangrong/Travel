<template>
    <div class="header">
        城市选择
        <router-link to='/'>
            <div class="iconfont header-icon">&#xe624;</div>
        </router-link>
    </div>
</template>
<script>
export default {
    name: 'cityHeader'
}
</script>
<style scoped>
    .header {
        overflow: hidden;
        line-height: 0.86rem;
        height: 0.86rem;
        text-align: center;
        color: #fff;
        font-size: 0.4rem;
        background-color: #00bcd4;
        position: relative;
    }
    .header-icon {
        width: 0.64rem;
        text-align: center;
        font-size: 0.4rem;
        position: absolute;
        top: 0;
        left: 0;
        color: #fff;
    }
</style>
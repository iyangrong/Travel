<template>
    <div class="search">
        <input class="search-input" type="text" placeholder="输入城市名或拼音" />
    </div>
</template>
<script>
export default {
    name: 'CitySearch'
}
</script>
<style scoped>
    .search {
        height: .72rem;
        background-color: #00bcd4;
        padding: 0 .1rem;
    }
    .search-input {
        height: 0.62rem;
        line-height: 0.62rem;
        width: 100%;
        text-align: center;
        border-radius: 0.06rem;
        color: #666;
        padding:0 0.1rem;
        box-sizing: border-box;
    }
</style>
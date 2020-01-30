<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe624;</div>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市/景点/游玩主题
        </div>
        <router-link to='/city'>
            <div class="header-right">
                {{city}}
                <span class="iconfont arrow-icon">&#xe64a;</span>
            </div>
        </router-link>
    </div>
</template>
<script>
export default {
    name: 'HomeHeader',
    props: {
        city: String
    }
}
</script>
<style scoped>
  .header {
      display: flex;
      line-height: .86rem;
      background: #00bcd4;
      color: #ffffff;
  }
  .header-left  {
      width: 0.64rem;
      float: left;
  }
  .header-input {
      flex: 1;
      height: 0.64rem;
      line-height: 0.64rem;
      margin-top: .12rem;
      margin-left: .12rem;
      background: #ffffff;
      border-radius: 0.1rem;
      color: #ccc;
      padding-left: .2rem;
  }
    .header-right {
        width: 1.24rem;
        float: right;
        text-align: center;
        color: white;
    } 
    .back-icon {
        text-align: center;
        font-size: .4rem;
    } 
    .arrow-icon {
        font-size: .2rem;
    } 
</style>
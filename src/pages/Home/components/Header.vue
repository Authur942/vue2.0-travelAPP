<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题</div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
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
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  display flex
  line-height $headerHeight
  background $bgcolor
  color #fff

.header-left
  width .64rem
  float left
  .back-icon
    text-align center
    font-size .4rem

// 搜索框
.header-input
  flex 1
  color #ccc
  height .64rem
  line-height .64rem
  margin-top .12rem
  margin-left .2rem
  padding-left .2rem
  background-color #ffffff
  border-radius .1rem

.header-right
  width 1.24rem
  float right
  text-align center
  color #ffffff
  .arrow-icon
    margin-left -.04rem
    font-size .24rem

</style>

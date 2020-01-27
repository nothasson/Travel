<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      城市
      <span class="iconfont icon-arrow">&#xe61f;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeHeader"
};
</script>
<style lang ="stylus" scoped>
@import '~styles/varibles.styl';

.header {
  line-height: 0.86rem;
  display: flex;
  background: $bgColor;
  color: #fff;

  .header-left {
    width: 0.64rem;
    float: left;
  }

  .header-input {
    flex: 1;
    background: #fff;
    border-radius: 0.1rem;
    line-height: 0.64rem;
    height: 0.64rem;
    margin-top: 0.12rem;
    margin-left: 0.2rem;
    padding-left: 0.2rem;
    color: grey;
    text-align: left;
    font-size: 0.3rem;
  }

  .header-right {
    width: 1.24rem;
    float: right;
    text-align: center;
    font-size: 0.3rem;

    .icon-arrow {
      margin-left: -0.04rem;
    }
  }
}
</style>

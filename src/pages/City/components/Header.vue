<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "CityHeader",
  data() {
    return {};
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header {
  position: relative;
  height: $headerHeight;
  line-height: $headerHeight;
  overflow: hidden;
  text-align: center;
  font-size: 0.32rem;
  color: #fff;
  background: $bgColor;

  .header-back {
    color: white;
    top: 0;
    left: 0;
    position: absolute;
    width: 0.64rem;
    text-align: center;
    font-size: 0.4rem;
  }
}
</style>
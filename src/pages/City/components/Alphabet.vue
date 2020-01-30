<template>
  <ul class="list">
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
  </ul>
</template>

<script>
export default {
  name: "CityAlphabet",
  data() {
    return {};
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.list {
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: 0.4rem;
  font-size: 0.24rem;

  .item {
    line-height: 0.4rem;
    color: $bgColor;
  }
}
</style>
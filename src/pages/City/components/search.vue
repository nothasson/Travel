<template>
  <div class="search">
    <input type="text" placeholder="输入城市名或拼音" class="search-input" />
  </div>
</template>

<script>
export default {
  name: "CitySearch"
};
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.search {
  padding: 0 0.1rem;
  height: 0.72rem;
  background: $bgColor;

  .search-input {
    box-sizing: border-box;
    height: 0.62rem;
    line-height: 0.62rem;
    padding: 0 0.1rem;
    width: 100%;
    border-radius: 0.06rem;
    color: #666;
    border-style: none;
    text-align: center;
  }
}
</style>
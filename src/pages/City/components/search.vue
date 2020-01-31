<template>
  <div>
    <div class="search">
      <input v-model="keyword" type="text" placeholder="输入城市名或拼音" class="search-input" />
    </div>
    <div class="search-content" v-show="keyword" ref="search">
      <ul>
        <li
          class="search-item border-bottom"
          v-for="item of list"
          :key="item.id"
          @click="handleCityClick(item.name)"
        >{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from "better-scroll";

export default {
  name: "CitySearch",
  data() {
    return {
      keyword: "",
      list: [],
      timer: null
    };
  },
  methods: {
    handleCityClick(city) {
      this.$store.dispatch("changeCity", city);
      this.$router.push("/");
    }
  },
  computed: {
    hasNoData() {
      return !this.list.length;
    }
  },
  props: {
    cities: Object
  },
  mounted() {
    this.scroll = new BScroll(this.$refs.search);
  },
  watch: {
    keyword() {
      if (this.timer) {
        clearTimeout(this.timer);
      }
      if (!this.keyword) {
        this.list = [];
        return;
      }
      this.timer = setTimeout(() => {
        const result = [];
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (
              value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1
            ) {
              result.push(value);
            }
          });
        }
        this.list = result;
      }, 100);
    }
  }
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

.search-content {
  z-index: 1;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  overflow: hidden;
  bottom: 0;
  background: #eee;

  .search-item {
    line-height: 0.62rem;
    padding-left: 0.2rem;
    color: #666;
    font-size: 0.3rem;
    background: #fff;
    text-align: left;
  }
}
</style>
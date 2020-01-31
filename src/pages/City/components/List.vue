<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.currentCity}}</div>
          </div>
        </div>
      </div>

      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div
            class="button-wrapper"
            v-for="item of hotCities"
            :key="item.id"
            @click="handleCityClick(item.name)"
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div
          class="item-list"
          v-for="city of item"
          :key="city.id"
          @click="handleCityClick(city.name)"
        >
          <div class="item border-bottom">{{city.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from "better-scroll";
import { mapState,mapMutations } from "vuex";

export default {
  name: "CityList",
  computed:{
    ...mapState({
      currentCity:'city'
    })
  },
  mounted() {
    this.scroll = new BScroll(this.$refs.wrapper);
  },
  
  props: {
    hotCities: Array,
    cities: Object,
    letter: String
  },
  watch: {
    letter() {
      if (this.letter) {
        const element = this.$refs[this.letter][0];
        this.scroll.scrollToElement(element);
      }
    }
  },
  methods: {
    handleCityClick(city) {
      this.changeCity(city);
      this.$router.push("/");
    },
    ...mapMutations(['changeCity'])
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.list {
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;

  .border-topbottom {
    &:before {
      border-color: #ccc;
    }

    &:after {
      border-color: #ccc;
    }
  }

  .border-bottom {
    &:before {
      border-color: #ccc;
    }
  }

  .title {
    line-height: 0.44rem;
    background: #eee;
    padding-left: 0.2rem;
    color: #666;
    font-size: 0.26rem;
  }

  .button-list {
    overflow: hidden;
    padding: 0.1rem 0.6rem 0.1rem 0.1rem;

    .button-wrapper {
      float: left;
      width: 33%;

      .button {
        text-align: center;
        font-size: 0.24rem;
        padding: 0.1rem 0;
        margin: 0.1rem;
        border: 0.02rem solid #ccc;
        border-radius: 0.06rem;
      }
    }
  }

  .item-list {
    .item {
      line-height: 0.76rem;
      // color: #666;
      padding-left: 0.2rem;
      text-align: left;
      font-size: 0.24rem;
    }
  }
}
</style>
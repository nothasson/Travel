<template>
  <div>
    <home-header></home-header>
    <home-swiper :swiperList="swiperList"></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-recommend :recommendList="recommendList"></home-recommend>
    <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>
<script>
import HomeHeader from "./components/Header";
import HomeSwiper from "./components/swiper";
import HomeIcons from "./components/icons";
import HomeRecommend from "./components/recommend";
import HomeWeekend from "./components/weekend";
import axios from "axios";
import {mapState} from 'vuex'

export default {
  name: "Home",
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data() {
    return {
      lastCity:'',
      swiperList: [],
      iconList: [],
      recommendList: [],
      // topIcon: [],
      weekendList: []
    };
  },
  computed :{
    ...mapState(['city'])
  },
  methods: {
    getCityInfo() {
      axios.get("/api/index.json?city=" + this.city).then(this.getCityInfoSucc);
    },
    getCityInfoSucc(res) {
      res = res.data;
      if (res.ret && res.data) {
        const data = res.data;
        this.swiperList = data.swiperList;
        this.iconList = data.iconList;
        this.recommendList = data.recommendList;
        // this.topIcon = data.topIcon;
        this.weekendList = data.weekendList;
      }
    }
  },
  mounted() {
    this.lastCity = this.city
    this.getCityInfo();
  },
  activated(){
    if(this.lastCity !== this.city){
      this.getCityInfo();
      this.lastCity = this.city;
    }
  }
};
</script>

<style>
</style>

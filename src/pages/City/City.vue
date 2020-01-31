<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :hotCities="hotCities" :cities="cities" :letter="letter"></city-list>
    <city-alphabet :cities="cities" @change="handleLetterChange"></city-alphabet>
  </div>
</template>

<script>
import CityHeader from "./components/Header";
import CitySearch from "./components/Search";
import CityList from "./components/List";
import CityAlphabet from "./components/Alphabet";
import axios from "axios";

export default {
  name: "City",
  data() {
    return {
      hotCities: [],
      cities: {},
      letter: ""
    };
  },
  computed: {
    letters() {
      const letters = [];
      for (let i in this.cities) letters.push(i);
      return letters;
    }
  },
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  methods: {
    getHomeInfo() {
      axios.get("/api/city.json").then(this.getHomeInfoSucc);
    },
    getHomeInfoSucc(res) {
      res = res.data;
      if (res.ret && res.data) {
        const data = res.data;
        this.hotCities = data.hotCities;
        this.cities = data.cities;
      }
    },
    handleLetterChange(letter) {
      this.letter = letter;
      //console.log(this.letter);
    }
  },
  mounted() {
    this.getHomeInfo();
  }
};
</script>

<style lang="stylus" scoped></style>
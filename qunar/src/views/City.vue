<template>
  <div>
    <city-header />
    <city-search :cities="cities" />
    <city-list :cities="cities" :hot="hotCities" :letter="letter" />
    <city-alphabet :cities="cities" @change="handleLetterChange" />
  </div>
</template>

<script>
import CityHeader from '../components/city/Header'
import CitySearch from '../components/city/Search'
import CityList from '../components/city/List'
import CityAlphabet from '../components/city/Alphabet'
import axios from 'axios'

export default {
  name: 'City',
  data() {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  methods: {
    getCityInfo() {
      axios.get('/api/city.json')
        .then(this.handleGetCityInfoSucc)
    },
    handleGetCityInfoSucc(res) {
      res = res.data
      if (res.ret) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    handleLetterChange(letter) {
      this.letter = letter
    }
  },
  mounted() {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list
      :cities="cities"
      :hotCities="hotCities"
      :letter="letter"
    ></city-list>
    <city-alphabet :cities="cities" @change="handleLetterChange"></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import cityHeader from './components/Header'
import citySearch from './components/Search'
import cityList from './components/List'
import cityAlphabet from './components/Alphabet'
export default {
  name: 'city',
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  components: {
    cityHeader,
    citySearch,
    cityList,
    cityAlphabet
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.getCityInfoSucc)
    },
    getCityInfoSucc (res) {
      console.log(res)
      res = res.data
      if (res.ret && res.data) {
        this.cities = res.data.cities
        this.hotCities = res.data.hotCities
      }
    },
    handleLetterChange (letter) {
      console.log(letter)
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>

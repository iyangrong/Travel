<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :cities="cities" :hotCities="hotCities"></city-list>
        <city-alphabet :cities="cities"></city-alphabet>
    </div>
</template>
<script>
import axios from 'axios'

import CityHeader from './components/Header.vue'
import CitySearch from './components/Search.vue'
import CityList from './components/List.vue'
import CityAlphabet from './components/Alphabet.vue'

export default {
    name: 'City',
    components: {
        CityHeader,
        CitySearch,
        CityList,
        CityAlphabet
    },
    data() {
        return {
            cities: {},
            hotCities: []
        }
    },
    mounted() {
        this.getCityInfo()
    },
    methods: {
        getCityInfo() {
            axios.get('/static/mock/city.json')
            .then(this.handleGetCityInfoSucc)
        },
        handleGetCityInfoSucc(res) {
            res = res.data
            if(res.ret && res.data) {
                this.cities = res.data.cities
                this.hotCities = res.data.hotCities
            }
        }
    }
}
</script>
<style scoped>

</style>
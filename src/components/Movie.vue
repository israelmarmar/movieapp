<template>
  <v-container>
    <v-layout row wrap>
      <v-flex xs12>
        <h2>welcome to single movie component</h2>
          <div>{{singleMovie}}</div>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
import axios from 'axios'
export default {
  props: ['id'],
  data () {
    return {
      singleMovie: ''
    }
  },
  mounted () {
    axios
      .get('http://www.omdbapi.com/?apikey=293df754&i='+this.id+'&Content-Type=application/json')
      .then(response => {
        console.log("oimovie")
        this.singleMovie = response.data
      })
      .catch(error => {
        console.log(error)
      })
  }
}
</script>
<style>
</style>

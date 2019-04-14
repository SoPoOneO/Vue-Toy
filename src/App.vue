<template>
  <div id="app">
    <Box v-for="(color, key) in boxColors" :key="key" :color="color" @click="clickBox(key)"></Box>

    <p>Red Count: {{ redCount }}</p>
    <p>Blue Count: {{ blueCount }}</p>
  </div>
</template>

<script>
import Box from './components/Box.vue';

export default {
  name: 'app',
  components: {
    Box
  },
  methods: {
    clickBox: function(i){
      var newColor = this.boxColors[i] == "red" ? "blue" : "red";
      this.$set(this.boxColors, i, newColor);
    }
  },
  computed: {
    redCount: function(){
      var count = 0;
      this.boxColors.forEach(function(color){
        if(color == "red"){
          count ++;
        }
      });
      return count;
    },
    blueCount: function(){
      var count = 0;
      this.boxColors.forEach(function(color){
        if(color == "blue"){
          count ++;
        }
      });
      return count;
    }
  },
  data: function(){
    return {
      boxColors: [
        "blue",
        "blue",
        "blue",
        "blue",
        "blue",
        "blue"
      ]
    }
  }
}
</script>

<style>
</style>

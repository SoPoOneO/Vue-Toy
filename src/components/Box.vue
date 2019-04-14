<template>
  <div :style="{ backgroundColor: this.color }" @click="$emit('click')">
    <h3>click me</h3>
  </div>
</template>

<script>
export default {
  props: ['color']
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  div {
    width: 100px;
    height: 200px;
    border: 2px solid grey;
    margin: 15px;
    padding: 10px;
    display: inline-block;
    box-sizing: border-box;
  }
</style>

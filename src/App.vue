<template>
  <img
    alt="Vue logo"
    src="./assets/logo.svg"
    v-on:mousemove="change"
    v-bind:style="{ filter: `grayscale(${offsetPerc})`}"
  >
</template>

<script>
import './styles.css'

export default {
  name: 'App',
  data() {
    return {
      offsetPerc: '0%',
    }
  },
  methods: {
    change: function (event) {
      const sorted = [event.x, event.y].sort((a, b) => a - b)
      const perc =  100 * Math.abs(sorted[0] / sorted[1])
      this.offsetPerc = `${perc}%`
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color:floralwhite;
}
</style>

<style scoped>
#app > img {
  height: 66%;
  width: 66%;
  filter: grayscale(0%);
}
</style>

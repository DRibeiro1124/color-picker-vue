<template>
  <div id="app">
    <img class="logo" :style="logoStyle" alt="PickerLogo" src="./assets/ColorPickerLogo.jpg">
    <ColorPicker />
  </div>
</template>

<script>
import ColorPicker from './components/ColorPicker.vue'

export default {
  name: 'app',
  components: {
    ColorPicker
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.logo {
  height: 15em;
}
</style>

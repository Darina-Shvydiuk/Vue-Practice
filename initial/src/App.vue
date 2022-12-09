<template>
  <MyComponent/>
  <HwCounter/>
</template>

<script>
import MyComponent from './components/lesson0/MyComponent.vue'
import HwCounter from './components/lesson0/HwCounter.vue'

export default {
  name: 'App',
  components: {
    MyComponent,
    HwCounter
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
  margin-top: 60px;
}
</style>

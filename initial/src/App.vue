<template>
  <MyComponent/>
  <HwCounter/>
  <UserCard/>
  <HwSearchProject/>
  <PhotoRedactor/>
  <ProductList/>
  <UserForm/>
</template>
<script>
import MyComponent from './components/lesson0/MyComponent.vue'
import HwCounter from './components/lesson0/HwCounter.vue'
import UserCard from './components/lesson1/UserCard.vue'
import HwSearchProject from './components/lesson1/HwSearchProject.vue'
import PhotoRedactor from './components/lesson2/PhotoRedactor.vue'
import ProductList from './components/lesson3/ProductList.vue'
import UserForm from './components/lesson4/UserForm.vue'

export default {
  name: 'App',
  components: {
    MyComponent,
    HwCounter,
    UserCard,
    HwSearchProject,
    PhotoRedactor,
    ProductList,
    UserForm
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

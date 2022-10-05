<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <div class="container">
      <div class="row g-3">
        <Products/>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Products from "@/components/Products";

export default {
  name: 'HomeView',
  components: {
    Products,
    HelloWorld,
  }
}
</script>

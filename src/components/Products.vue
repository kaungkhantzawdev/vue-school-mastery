<template>
  <div class="col-lg-6" v-for="post in data.products" :key="post.id">
    <div class="d-flex align-items-center justify-content-between px-3 py-2 border rounded">
      <div class="me-5">
        <p class="mb-0 text-black-50 test-sm">{{ post.brand}}</p>
        <div class="my-3">
          <img :src="post.thumbnail" alt="" class="rounded-circle" style="width: 100px; height: 100px; object-position: center; object-fit: cover">
        </div>
        <p class="mb-0">{{ post.stock}}</p>
      </div>
      <div class="text-start w-100">
        <h4 class="">
          {{ post.title }}
        </h4>
        <p class="text-black-50">
          {{ post.description }}
        </p>
        <span>{{ post.rating}}</span>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: "Products",

  data() {
    return {
      data: ""
    }
  },
  methods: {
    name() {

    }
  },
  created() {
    axios.get('https://dummyjson.com/products')
      .then(res => {
        this.data = res.data
        console.log(this.data)
      })
  }
}
</script>

<style scoped>

</style>
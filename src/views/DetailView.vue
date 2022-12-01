<template>
  <div class="container">
    <div class="row g-3">
      <div class="col" v-if="post">
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
      <div class="col" v-else>
        <div class="d-flex align-items-center justify-content-between px-3 py-2 border rounded">
          Not found detail post
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: "Products",
  props: ['id'],
  data() {
    return {
      post: ""
    }
  },
  created() {
    axios.get('https://dummyjson.com/products/'+ this.id)
        .then(res => {
          this.post = res.data
          console.log(this.post)
        })
  }
}
</script>

<style scoped>

</style>
<template>
  <div class="row g-3">
    <div class="col-lg-6" v-for="post in posts" :key="post.id">
    <div class="d-flex align-items-center justify-content-between px-3 py-2 border rounded">
      <div class="me-5">
        <p class="mb-0 text-black-50 test-sm">{{ post.brand}}</p>
        <div class="my-3">
          <img :src="post.thumbnail" alt="" class="rounded-circle" style="width: 100px; height: 100px; object-position: center; object-fit: cover">
        </div>
        <p class="mb-0">{{ post.stock}}</p>
      </div>
      <div class="text-start w-100">
        <router-link :to="{ name: 'detail', params: { id: post.id}}">
          <h4 class="">
            {{ post.title }}
          </h4>
        </router-link>
        <p class="text-black-50">
          {{ post.description }}
        </p>
        <span>{{ post.rating}}</span>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: "Products",
  props:{
    posts: {
      required: true,
      type: Array
    }
  }
}
</script>

<style scoped>

</style>
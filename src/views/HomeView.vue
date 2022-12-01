<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h4>
      {{ day }}
    </h4>
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <div class="container">
        <Posts :posts="data"/>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Posts from "@/components/Posts"
import axios from "axios";
import dayjs from "dayjs";
import customParseFormat from "dayjs/plugin/customParseFormat";
import relativeTime from "dayjs/plugin/relativeTime"
dayjs.extend(relativeTime)
dayjs.extend(customParseFormat);

export default {
  name: 'HomeView',
  components: {
    Posts,
  },
  data() {
    return {
      data: [],
      d: new Date(),
      day : dayjs().to(dayjs('2022-08-01'))
    }
  },
  created() {
    axios.get('https://dummyjson.com/products')
        .then(res => {
          this.data = res.data.products
          console.log(this.data)
        })
  }
}
</script>

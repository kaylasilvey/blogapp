<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="post in posts"></div>
    <h1>{{ post.title }}</h1>
    <p>{{ post.body }}</p>
    <img src="" />
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      message: "Welcome to BLOG!",
      posts: [],
      title: "",
      body: ""
    };
  },
  created: function() {
    axios.get("/api/posts").then(response => {
      this.posts = response.data;
      console.log(this.posts);
    });
  },
  methods: {}
};
</script>

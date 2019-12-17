<template>
  <div class="posts-index">
    <h1>{{ message }}</h1>

    <div v-for="post in posts">
      <p>{{post}}</p>
      <p>title: {{post.title}}</p>
      <p>body: {{post.body}}</p>
      <p>image: {{post.image}}</p>
    </div>

  </div>
</template>

<style>
</style>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      message: "Welcome to Posts Index!",
      posts:[]
    };
  },
  created: function() {
    axios.get("/api/posts").then(response => {
      console.log(response.data);
      this.posts = response.data;
    });
  },
  methods: {}
};
</script>


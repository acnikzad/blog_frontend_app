<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h1>{{post.title}}</h1>
    <h1>{{post.body}}</h1>
    <h1>{{post.image}}</h1>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Welcome to Second!"
    };
  },
  created: function() {},
  methods: {}
};
</script>
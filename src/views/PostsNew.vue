<template>
  <div class="posts-new">
    <div class="container">
      <form v-on:submit.prevent="submit()">
        <h1>Make a New Post</h1>
        <div class="form-group">
          <label>Title:</label>
          <input type="text" class="form=control" v-model="title">
        </div>
        <div class="form-group">
          <label>Body:</label>
          <input type="text" class="form=control" v-model="title">
        </div>
        <div class="form-group">
          <label>Image:</label>
          <input type="text" class="form=control" v-model="title">
        </div>
      </form>
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
      user_id: this.user_id,
      title: this.title,
      body: this.body,
      image: this.image
    };
  },

  methods: {
    submit: function() {
      var params = {
        title: this.title,
        body: this.body,
        image: this.image,
      };

      axios
        .post("/api/posts", params)
        .then(reponse => {
          this.$router.push("/posts");
        })
        .catch(error => {
          this.errors = error.reponse.data.errors;
        });
    }
  }
};
</script>
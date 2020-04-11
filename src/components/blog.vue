<template>
  <div>
    <h1>Articles</h1>
    <div v-for="post in blogdata" :key="post.id">{{post.title}}</div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  data() {
    return {
      blogdata: []
    };
  },
  created() {
    axios
      .get(
        // API KEy : https://developers.google.com/blogger/docs/3.0/using#WorkingWithBlogs
        // BlogID : open your blogspot account
        "https://www.googleapis.com/blogger/v3/blogs/8060917798751958753/posts?key=AIzaSyBEhx__zclxQ4YqzZCaxHfNaf5pmNjxfIk"
      )
      .then(Response => {
        console.log(Response);
        this.blogdata = Response.data.items;
      })
      .catch(Error => {
        console.log(Error);
      });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

<template>
  <PostList />
</template>

<script>
import PostListVue from "./components/PostList.vue";
export default {
  name: "App",
  components: {
    PostList: PostListVue,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

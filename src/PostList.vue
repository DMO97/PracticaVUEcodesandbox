<template>
  <div>
    <div v-for="post in posts" :key="post.id">
      <h3>{{ post.title }}</h3>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "PostList",

  data() {
    return {
      posts: [],
    };
  },

  methods: {
    async getPosts() {
      let url = "https://jsonplaceholder.typicode.com/posts";
      let response = await axios.get(url);
      this.posts = response.data;
    },

    async postData() {
      let post = {
        body: "Hola jake",
      };
      let url = "https://jsonplaceholder.typicode.com/posts";
      let response = await axios.get(url, post);
    },
  },

  //Esta bloque nos permite inicializar el modulo, donde estamos recibiendo
  //los datos del API esperando las promesas, se añade una condicional
  //para indicar que si la peticion fue correcta se pintaran
  //en caso contrario se envia una alerta y el status de la peticion
  created() {
    this.getPosts();
    this.postData();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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

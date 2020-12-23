<template>
  <h1>Articulo - {{ $route.params.id }}</h1>

  <h3>
    {{ postData.title }}
  </h3>

  <p>
    {{ postData.body }}
  </p>

  <router-link class="back" :to="'/blog'"> Back </router-link>
</template>

<script>
export default {
  data() {
    return {
      postData: [],
    };
  },
  created() {
    this.getData();
  },
  methods: {
    async getData() {
      const routeFinal = `https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`;
      const fetchData = await fetch(routeFinal);

      const jsonData = await fetchData.json();

      this.postData = jsonData;
    },
  },
};
</script>

<style scoped>
.back {
  color: snow;
  background-color: #42b983;
  font-weight: bolder;
  padding: 5px;
  border-radius: 6px;
  text-decoration: none;
  font-size: 1.2rem;
}
</style>
<template>
  <div>
    <h1>Ultimos Posts</h1>

    <div v-for="post in postData" :key="post.id">
      <router-link class="link" :to="`/blog/${post.id}`">
        {{ post.title }}
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      postData: [],
    };
  },
  created() {
    this.getPost();
  },
  methods: {
    async getPost() {
      try {
        const fetchData = await fetch(
          "https://jsonplaceholder.typicode.com/posts"
        );

        const jsonData = await fetchData.json();

        this.postData = jsonData;
      } catch (err) {
        console.log(err);
      }
    },
  },
};
</script>

<style scoped>
.link {
  background-color: dodgerblue;
  color: snow;
  padding: 5px;
  display: block;
  margin: 10px 0;
  border-radius: 5px;
  text-decoration: none;
}
</style>
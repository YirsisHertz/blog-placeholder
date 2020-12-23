<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Hello />
  </div>
</template>

<script>
// @ is an alias to /src
import Hello from "@/components/Hello";

export default {
  name: "Home",
  components: {
    Hello,
  },
};
</script>

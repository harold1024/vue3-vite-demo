<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
  <List />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import List from "./components/list.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    List,
  },
};
</script>

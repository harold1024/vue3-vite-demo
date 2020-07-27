<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
  <Composition />
  <AsyncSuspense />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Composition from "./components/Composition.vue";
import AsyncSuspense from "./components/Suspense/index.vue"

export default {
  name: "App",
  components: {
    HelloWorld,
    Composition,
    AsyncSuspense,
  },
};
</script>

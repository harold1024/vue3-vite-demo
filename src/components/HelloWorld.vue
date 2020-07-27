<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <div>{{ state.count1 }}</div>
  <p>
    Edit <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script>
import { reactive } from "vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  setup() {
    const state = reactive({
      count1: 1,
    });
    return { state };
  },
  data() {
    return {
      count: 0,
    };
  },
};
</script>

<template>      
<!-- 新增组件Fragment,Suspense, Teleport -->


  <!-- fragment就是以后vue组件不需要一个根节点了 -->

  <!-- Suspense可以更好的实现异步组件的方式 -->
  <h1>Supense</h1>
  <Suspense>
    <template #default>
      <AsyncComponent :timeout="3000" />
    </template>
    <template #fallback>
      <Loading />
    </template>
  </Suspense>

  <!-- Teleport等同与React的Portal,只不过chrome浏览器准备把Portal增加为原生的元素,就是可以渲染vue组件内容到指定的dom节点上 -->
  <Protal />
</template>

<script>
import Protal from "./Portal.vue"
import AsyncComponent from "./AsyncComponent.vue";
import Loading from "./Loading.vue";
export default {
  components: {
    Protal,
    AsyncComponent,
    Loading,
  },
};
</script>

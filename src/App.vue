<template>
  <div>
    <!-- <DataComp /> -->

    <!-- <DemoOne /> -->
    <!-- <DemoTwo /> -->

    <MethodsComp />
  </div>
</template>

<script>
// import DataComp from "./components/DataComp.vue";
// import DemoOne from "./components/DemoOne.vue";
// import DemoTwo from "./components/DemoTwo.vue";
import MethodsComp from "./components/MethodsComp.vue";

export default {
  name: "App",
  components: {
    // DataComp,
    // DemoOne,
    // DemoTwo,
    MethodsComp,
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

<template>
  <div>
    <!-- <DataComp /> -->
    <!-- <DemoOne /> -->
    <DemoTwo />
  </div>
</template>

<script>
// import DataComp from "./components/DataComp.vue";
// import DemoOne from "./components/DemoOne.vue";
import DemoTwo from "./components/DemoTwo.vue";

export default {
  name: "App",
  components: {
    // DataComp,
    // DemoOne,
    DemoTwo,
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

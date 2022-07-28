<template>
  <div>
    <!-- <DataComp /> -->

    <!-- <DemoOne /> -->
    <!-- <DemoTwo /> -->

    <!-- <MethodsComp /> -->

    <!-- <VModel /> -->

    <!-- <ComputedComp /> -->

    <!-- <WatchComp /> -->

    <!-- <ProvideInject /> -->

    <!-- <TemplateRef /> -->

    <!-- <PersonComp /> -->

    <ClickedCounter />
    <HoveredCounter />
  </div>
</template>

<script>
// import DataComp from "./components/DataComp.vue";
// import DemoOne from "./components/DemoOne.vue";
// import DemoTwo from "./components/DemoTwo.vue";
// import MethodsComp from "./components/MethodsComp.vue";
// import VModel from "./components/VModel.vue";
// import ComputedComp from "./components/ComputedComp.vue";
// import WatchComp from "./components/WatchComp.vue";
// import ProvideInject from "./components/ProvideInject.vue";
// import TemplateRef from "./components/TemplateRef.vue";
// import PersonComp from "./components/PersonComp.vue";
import ClickedCounter from "./components/ClickedCounter.vue";
import HoveredCounter from "./components/HoveredCounter.vue";

export default {
  name: "App",
  components: {
    // DataComp,
    // DemoOne,
    // DemoTwo,
    // MethodsComp,
    // VModel,
    // ComputedComp,
    // WatchComp,
    // ProvideInject,
    // TemplateRef,
    // PersonComp,
    ClickedCounter,
    HoveredCounter,
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

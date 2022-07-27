<template>
  <div>
    <h2>Options - {{ o_firstname }}</h2>
    <h2>Composition - {{ c_firstname }}</h2>
    <h2>Composition - {{ greet }}</h2>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "DataComp",
  setup() {
    const c_firstname = ref("Clark");
    const greet = `Hello ${c_firstname.value}`;
    console.log(c_firstname);
    return {
      c_firstname,
      greet,
    };
  },
  data() {
    return {
      o_firstname: "Bruce",
    };
  },
};
</script>

<style scoped></style>

<template>
  <div>
    <h3>Child A Component</h3>
    <ChildB />
  </div>
</template>

<script>
import ChildB from "./ChildB.vue";
export default {
  name: "ChildA",
  components: {
    ChildB,
  },
};
</script>

<style scoped></style>

<template>
  <div>
    <h3>Child B Component</h3>
    <ChildC />
  </div>
</template>

<script>
import ChildC from "./ChildC.vue";
export default {
  name: "ChildB",
  components: {
    ChildC,
  },
};
</script>

<style scoped></style>

<template>
  <div>
    <h3>Child C Component</h3>
    <h4>Child C component username {{ username }}</h4>
    <h4>Child C component composition username {{ childeUsername }}</h4>
    <h4>Child C component composition count {{ count }}</h4>
    <h4>Child C component composition hero {{ firstName }} {{ lastName }}</h4>
    <button @click="incrementCount">Increment count from child</button>
  </div>
</template>

<script>
import { inject, toRefs } from "vue";
export default {
  name: "ChildC",
  setup() {
    const childeUsername = inject("c_username", "Default username");
    const count = inject("c_count", 0);
    const state = inject("c_state", {});
    const incrementCount = inject("incrementCount");

    return {
      childeUsername,
      count,
      ...toRefs(state),
      incrementCount,
    };
  },
  inject: ["username"],
};
</script>

<style scoped></style>

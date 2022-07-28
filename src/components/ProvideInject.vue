<template>
  <div>
    <h4>Parent component name {{ name }}</h4>
    <h4>Parent component count {{ count }}</h4>
    <h4>Parent component hero {{ firstName }} {{ lastName }}</h4>
    <h3>Parent Component</h3>
    <button @click="incrementCount">Increment count</button>
    <ChildA />
  </div>
</template>

<script>
import { provide, reactive, ref, toRefs } from "vue";

import ChildA from "./ChildA.vue";
export default {
  name: "ProvideInject",
  components: {
    ChildA,
  },
  setup() {
    provide("c_username", "Codevolution");

    const count = ref(0);
    const state = reactive({
      firstName: "Bruce",
      lastName: "Wayne",
    });

    provide("c_count", count);
    provide("c_state", state);

    function incrementCount() {
      count.value++;
    }

    provide("incrementCount", incrementCount);

    return {
      count,
      ...toRefs(state),
      incrementCount,
    };
  },
  data() {
    return {
      name: "Shrikant",
    };
  },
  provide() {
    return {
      username: this.name,
    };
  },
};
</script>

<style scoped></style>

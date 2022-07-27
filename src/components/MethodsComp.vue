<template>
  <div>
    <h2>{{ name }}</h2>
    <button @click="changeName">change Name</button>

    <h2>{{ count }}</h2>
    <button @click="incrementCount">Increment</button>

    <h2>{{ firstName }} {{ lastName }}</h2>
    <button @click="changeHeroName">Change Hero</button>
  </div>
</template>

<script>
import { reactive, ref, toRefs } from "vue";
export default {
  name: "MethodsComp",
  setup() {
    const count = ref(0);

    function incrementCount() {
      count.value++;
    }

    const state = reactive({
      firstName: "Bruce",
      lastName: "Wayne",
    });

    function changeHeroName() {
      state.firstName = "Clark";
      state.lastName = "Kent";
    }

    return {
      count,
      incrementCount,
      ...toRefs(state),
      changeHeroName,
    };
  },
  data() {
    return {
      name: "Shrikant",
    };
  },
  methods: {
    changeName() {
      this.name = "Codevoltion";
    },
  },
};
</script>

<style scoped></style>

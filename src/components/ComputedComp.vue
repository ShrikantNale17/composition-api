<template>
  <div>
    <input type="text" placeholder="fName" v-model="fName" />
    <input type="text" placeholder="lName" v-model="lName" />
    <h2>Options Fullname is {{ fullName }}</h2>

    <input type="text" placeholder="refFirstName" v-model="refFirstName" />
    <input type="text" placeholder="refLastName" v-model="refLastName" />
    <h2>Composition Fullname is {{ refFullName }}</h2>

    <input
      type="text"
      placeholder="reactiveFirstName"
      v-model="reactiveFirstName"
    />
    <input
      type="text"
      placeholder="reactiveLastName"
      v-model="reactiveLastName"
    />
    <h2>Reactive Fullname is {{ reactiveFullName }}</h2>
  </div>
</template>

<script>
import { computed, reactive, ref, toRefs } from "vue";
export default {
  name: "ComputedComp",
  setup() {
    const refFirstName = ref("");
    const refLastName = ref("");

    const refFullName = computed(function () {
      return `${refFirstName.value} ${refLastName.value}`;
    });

    const state = reactive({
      reactiveFirstName: "",
      reactiveLastName: "",
    });

    const reactiveFullName = computed(function () {
      return `${state.reactiveFirstName} ${state.reactiveLastName}`;
    });

    return {
      refFirstName,
      refLastName,
      refFullName,
      ...toRefs(state),
      reactiveFullName,
    };
  },
  data() {
    return {
      fName: "",
      lName: "",
    };
  },
  computed: {
    fullName() {
      return `${this.fName} ${this.lName}`;
    },
  },
};
</script>

<style scoped></style>

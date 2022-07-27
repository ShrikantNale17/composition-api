<template>
  <div>
    <input type="text" placeholder="fName" v-model="fName" />
    <input type="text" placeholder="lName" v-model="lName" />

    <input type="text" placeholder="heroName" v-model="heroName" />
    <input type="text" placeholder="firstName" v-model="firstName" />
    <input type="text" placeholder="lastName" v-model="lastName" />
  </div>
</template>

<script>
import { reactive, ref, toRefs } from "vue";
export default {
  name: "VModel",
  setup() {
    const heroName = ref("");

    const state = reactive({
      firstName: "",
      lastName: "",
    });

    return {
      heroName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      fName: "",
      lName: "",
    };
  },
};
</script>

<style scoped></style>

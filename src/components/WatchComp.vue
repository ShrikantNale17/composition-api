<template>
  <div>
    <div>
      <input type="text" placeholder="name" v-model="name" />
    </div>
    <div>
      <input type="text" placeholder="firstName" v-model="firstName" />
      <input type="text" placeholder="lastName" v-model="lastName" />
    </div>
    <div>
      <input type="text" placeholder="reactive fName" v-model="fName" />
      <input type="text" placeholder="reactive lName" v-model="lName" />
      <input
        type="text"
        placeholder="reactive hero name"
        v-model="options.heroName"
      />
    </div>
  </div>
</template>

<script>
import _ from "lodash";
import { reactive, ref, toRefs, watch } from "vue";

export default {
  name: "WatchComp",
  setup() {
    const state = reactive({
      fName: "",
      lName: "",
      options: {
        heroName: "",
      },
    });

    /* watch(
      () => ({ ...state }),
      function (newValue, oldValue) {
        console.log("fName old value ", oldValue.fName);
        console.log("fName new value ", newValue.fName);
        console.log("lName old value ", oldValue.lName);
        console.log("lName new value ", newValue.lName);
      }
    ); */
    watch(
      () => _.cloneDeep(state.options),
      (newValue, oldValue) => {
        console.log("heroName old value ", oldValue);
        console.log("heroName new value ", newValue);
      },
      {
        deep: true,
      }
    );

    const firstName = ref("");
    const lastName = ref("Wayne");

    watch(
      [firstName, lastName],
      (newValue, oldValue) => {
        console.log(`oldValue of firstName - `, oldValue[0]);
        console.log(`newValue of firstName - `, newValue[0]);
        console.log(`oldValue of lastName - `, oldValue[1]);
        console.log(`newValue of lastName - `, newValue[1]);
      },
      {
        immediate: true,
      }
    );

    return {
      firstName,
      lastName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      name: "",
    };
  },
  watch: {
    name(newValue, oldValue) {
      console.log(`newValue - ${newValue}, oldValue - ${oldValue}`);
    },
  },
};
</script>

<style scoped></style>

<template>
  <div>
    <input type="text" placeholder="first name" v-model="firstName" />
    <input type="text" placeholder="last name" v-model="lastName" />
    <PersonGreeting
      :firstName="firstName"
      :lastName="lastName"
      @callHeroes="callHeroes"
    />
  </div>
</template>

<script>
import { ref } from "vue";
import PersonGreeting from "./PersonGreeting.vue";

export default {
  name: "PersonComp",
  components: {
    PersonGreeting,
  },
  setup() {
    const firstName = ref("");
    const lastName = ref("");

    function callHeroes(hero) {
      alert(`Hello ${hero}`);
    }

    return {
      firstName,
      lastName,
      callHeroes,
    };
  },
};
</script>

<style scoped></style>

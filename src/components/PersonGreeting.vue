<template>
  <div>
    <h4>Hello {{ fullName }}</h4>
  </div>
</template>

<script>
import { computed } from "vue";
export default {
  name: "PersonGreeting",
  props: ["firstName", "lastName"],
  setup(props) {
    const fullName = computed(() => {
      return `${props.firstName} ${props.lastName}`;
    });

    return {
      fullName,
    };
  },
  /* computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    },
  }, */
};
</script>

<style scoped></style>

<template>
  <div>
    <h4>Hello {{ fullName }}</h4>
    <button @click="sendEvent">Call hero</button>
  </div>
</template>

<script>
import { computed } from "vue";
export default {
  name: "PersonGreeting",
  props: ["firstName", "lastName"],
  setup(props, context) {
    console.log(context);
    const fullName = computed(() => {
      return `${props.firstName} ${props.lastName}`;
    });

    function sendEvent() {
      context.emit("callHeroes", fullName.value);
    }

    return {
      fullName,
      sendEvent,
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

<template>
  <div>
    <h2 @mouseover="incrementCount">Hovered {{ count }} times</h2>
  </div>
</template>

<script>
// import counter from "../mixins/counter";
import useCounter from "../composables/useCounter";

export default {
  name: "HoveredCounter",
  //   mixins: [counter],
  setup() {
    const { count, incrementCount } = useCounter();

    return {
      count,
      incrementCount,
    };
  },
};
</script>

<style scoped></style>

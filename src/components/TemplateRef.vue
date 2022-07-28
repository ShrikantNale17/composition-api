<template>
  <div>
    <input type="text" ref="inputRef" />
  </div>
</template>

<script>
import { onMounted, ref } from "vue";
export default {
  name: "TemplateRef",
  setup() {
    const inputRef = ref(null);

    onMounted(() => {
      inputRef.value.focus();
    });

    return {
      inputRef,
    };
  },
};
</script>

<style scoped></style>

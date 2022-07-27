<template>
  <div>
    <h2>Options - {{ o_firstname }}</h2>
    <h2>Options - {{ o_firstname }} {{ o_lastname }} a.k.a {{ o_heroname }}</h2>

    <h2>Composition - {{ c_firstname }}</h2>
    <h2>Composition - {{ greet }}</h2>

    <h2>Composition - {{ c_firstname }} {{ c_lastname }} {{ c_heroname }}</h2>
    <h2>Composition - {{ greetHero }}</h2>

    <h2>
      Composition - {{ state.c_firstname }} {{ state.c_lastname }}
      {{ state.c_heroname }}
    </h2>
    <h2>Composition - {{ reactiveGreetHero }}</h2>
  </div>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  name: "DataComp",
  setup() {
    const c_firstname = ref("Clark");
    const c_lastname = ref("Kent");
    const c_heroname = ref("Superman");

    const greet = `Hello ${c_firstname.value}`;
    const greetHero = `Hello ${c_firstname.value} ${c_lastname.value} ${c_heroname.value}`;
    console.log(c_firstname);

    const state = reactive({
      c_firstname: "Clark",
      c_lastname: "Kent",
      c_heroname: "Superman",
    });

    const reactiveGreetHero = `Hello ${state.c_firstname} ${state.c_lastname} a.k.a ${state.c_heroname}`;
    return {
      c_firstname,
      c_lastname,
      c_heroname,
      greet,
      greetHero,
      state,
      reactiveGreetHero,
    };
  },
  data() {
    return {
      o_firstname: "Bruce",
      o_lastname: "Wayne",
      o_heroname: "Batman",
    };
  },
};
</script>

<style scoped></style>

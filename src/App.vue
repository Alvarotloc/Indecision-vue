<template>
  <!-- <ContadorVue titulo="Entraron" :start="10" /> -->
  <IndecisionVue />
</template>

<script>
// import ContadorVue from "./components/Contador.vue";
import IndecisionVue from "./components/Indecision.vue";
export default {
  name: "InicioApp",
  components: {
    // ContadorVue,
    IndecisionVue,
  },
};
</script>

<style >
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>

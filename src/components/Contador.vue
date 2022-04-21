<template>
    <h1>Que papaia de contador</h1>
    <h3>(Ésta vez con Vue)</h3>
    <div class="contador">
      <h2>{{ customTitle }}</h2>
      <h4>{{ counter }}</h4>
      <section>
        <button @click="restarCount">Restar puntos</button>
        <button @click="resetCount">Resetear puntos</button>
        <button @click="sumarCount">Sumar puntos</button>
      </section>
      <h4>Al cuadrado: {{ squareCount }}</h4>
      <p v-if="error">No se puede restar al 0</p>
    </div>
</template>

<script>
export default {
  props: {
    titulo: String,
    start: {
      type: Number,
      required: false,
      default: 5,
      validator(value) {
        return value > 0 && value < 20;
      },
    },
  },
  name: "ContadorApp",
  data() {
    return {
      counter: this.start,
      error: false,
    };
  },
  methods: {
    sumarCount() {
      this.counter++;
      return (this.error = false);
    },
    resetCount() {
      this.counter = 0;
      return (this.error = false);
    },
    restarCount() {
      if (this.counter > 0) {
        this.counter--;
        return (this.error = false);
      }
      this.error = true;
    },
  },
  computed: {
    squareCount() {
      return this.counter * this.counter;
    },
    customTitle() {
      return this.titulo ? this.titulo : "Contador";
    },
  },
};
</script>

<style>
.inicio {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: rgb(3, 3, 46);
  color: white;
}
h1 {
  margin: 120px 0 30px 0;
  font-size: 3em;
}
h4 {
  color: white;
  font-size: 2em;
  margin: 30px 0;
}
h2 {
  color: white;
  font-size: 3em;
}
.contador {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 16vh;
}
button {
  margin: 0 20px;
  appearance: none;
  padding: 10px;
  border-radius: 10px;
  cursor: pointer;
  background: rgb(231, 231, 231);
  transition: all 0.4s;
}
button:hover {
  background: rgb(201, 201, 201);
}
</style>
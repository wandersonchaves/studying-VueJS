<template>
  <div class="monty-hall">
    <h1>Problema de Monty Hall</h1>
    <div class="form">
      <div v-if="!started">
        <label for="Quantas Portas?"></label>
        <input type="number" v-model.number="numberOfDoors" />
      </div>
      <div v-if="!started">
        <label for="Qual porta é premiada?"></label>
        <input type="number" v-model.number="selectedDoor" />
      </div>
      <button v-if="!started" @click="started = true">Iniciar</button>
      <button v-if="started" @click="started = false">Reiniciar</button>
    </div>
    <div class="doors" v-if="started">
      <div v-for="i in numberOfDoors" :key="i">
        <Door :number="i" :hasGift="i === selectedDoor" />
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import Door from "./components/Door";

export default {
  name: "App",
  components: { Door },
  setup() {
    const started = ref(false);
    const numberOfDoors = ref(10);
    const selectedDoor = ref(1);

    return { started, numberOfDoors, selectedDoor };
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

:root {
  --frame-border: 5px solid brown;
  --selected-border: 5px solid yellow;
}

body {
  color: #fff;
  background: linear-gradient(to right, rgb(21, 153, 87), rgb(21, 87, 153));
}

.monty-hall {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.monty-hall h1 {
  border: 1px solid #000;
  background-color: #0004;
  padding: 20px;
  margin-bottom: 60px;
}

.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 40px;
}

.form,
.form input,
.form button {
  margin-bottom: 10px;
  font-size: 2rem;
}

.doors {
  display: flex;
  justify-content: space-around;
}
</style>

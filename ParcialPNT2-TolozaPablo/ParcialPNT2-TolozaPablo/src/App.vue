<template>
  <div class="container mt-3">
    <div class="jumbotron">
      <h1>Parcial PNT2 - Pablo Toloza</h1>
      <br>
      <Parcial />
      
    </div>
  </div>
</template>

<script>
import Parcial from './componentes/Parcial.vue';

export default {
  name: 'App',
  components: {
    Parcial
  }
}
</script>

<style>
  h1 {
    color:rgb(106, 42, 165);
  }

  .jumbotron {
    padding-top: 40px;
    padding-bottom: 40px;
  }
</style>

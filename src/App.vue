<template>
  <div class="container">
    <h1>Random Git Cat</h1>
    <form>
      <div class="form-group">
        <label for="titulo">Titulo: </label>
        <input type="text" class="form-control" v-model="titulo">
      </div>
      <div class="form-group">
        <label for="filtro">Filtro:</label>
        <select class="form-control" v-model="filtro">
          <option value="blur">Desenfocado</option>
          <option value="mono">Monocromático</option>
          <option value="sepia">Sepia</option>
          <option value="negative">Negativo</option>
          <option value="paint">Efecto de Pintura</option>
        </select>
      </div>
      <div class="form-group">
        <label for="colores">Colores:</label>
        <select class="form-control" v-model="colores">
          <option value="red">Rojo</option>
          <option value="green">Verde</option>
          <option value="blue">Azul</option>
          <option value="yellow">Amarillo</option>
          <option value="white">Blanco</option>
        </select>
        <span :style="{backgroundColor: colores}">color de fondo</span>
      </div>
      <div class="form-group">
        <label for="tamano">Tamaño: </label>
        <input type="number" class="form-control" v-model="medida">
      </div>
      <button class="btn btn-primary" @click.prevent="buscar">Obtener mi gatito</button>
    </form>
    <HelloWorld :url="url"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() {
    return {
      titulo: 'Gato',
      filtro: 'blur',
      colores: 'red',
      medida: '300',
      url: ''
    }
  },
  components: {
    HelloWorld
  },
  methods: { 
    buscar(){
      if (this.titulo && this.medida){
        this.url = `https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.filtro}&color=${this.colores}&size=${this.medida}`;
        console.log(this.url);
      } else {
        alert("Ingrese valores validos");
      }
    } 
  }
}
</script>

<style>

</style>

<template>
  <div class="container">
    <div class="informacion">
      <label id="left">Puntaje: {{ puntaje }}</label>
      <label id="right">Intento: {{ intentos }}</label>
    </div>
    <div class="horizontal">
      <Casino valor="0" v-bind:validacion="iniciar"></Casino>
      <Casino valor="1" v-bind:validacion="iniciar"></Casino>
      <Casino valor="2" v-bind:validacion="iniciar"></Casino>
    </div>
    <div class="boton" > 
      <br>
      <button v-on:click="jugar()">JUGAR</button>
    </div>
    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Casino from './components/Casino.vue'

export default {
  data() {
    return {
      puntaje: 0,
      intentos: 0,
      iniciar:false
    }
  },
  methods:{
    jugar(){
            this.iniciar=true
        }
  },

  name: 'App',
  components: {
    HelloWorld,
    Casino
  }
}
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: block;
  align-items: center;
  text-align: center;
  margin-left: 25%;
  margin-right: auto;
}

.horizontal {
  display: flex;
}

.informacion {
  margin-left: -30%;
  margin-right: auto;
  display: block;
  text-align: center;
}

#right {
  margin-left: 200px;
}

.container {
  font-size: 30px;
}

button {
  margin-left: -30%;
  font-size: 30px;
}
</style>

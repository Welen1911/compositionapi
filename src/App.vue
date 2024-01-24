<template>
  {{ framework }}
  <img @click="melhorque()" alt="Vue logo" src="./assets/logo.png">
  {{ conjuncao }}
<HelloWorld v-if="showTecnologia" :msg="tecnologia"/>
<HelloWorld v-else msg="Ain VueJs não presta, ainnnnn"/>
<input type="text" v-model="tecnologia">
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      conjuncao: "É melhor que ",
      tecnologia: "",
      showTecnologia: false
    }
  },
  methods: {
    melhorque() {
      this.showTecnologia = !this.showTecnologia;
    }
  },
  setup() {
    
    const framework = "VueJs";

    return {
      framework
    };
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

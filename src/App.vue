<template>
  {{ framework }}
  <img @click="melhorque()" alt="Vue logo" src="./assets/logo.png">
  {{ conjuncao }}
<HelloWorld  :msg="showTecnologia ? tecnologia : 'Ain VueJs não presta, ainnnnn'"/>

<input type="text" v-model="user.firstName">
<h1>{{ user.firstName }}</h1>
</template>

<script>
import { ref } from 'vue';

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
      this.user.firstName = "Maverick"
    }
  },
  setup() {
    
    let user = ref({
      firstName: "Welen",
      lastName: "Almeida"
    });
    const framework = "VueJs";

    return {
      user,
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

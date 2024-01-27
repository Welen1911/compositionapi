<template>
  {{ framework }}
  <img @click="melhorque()" alt="Vue logo" src="./assets/logo.png">
  {{ conjuncao }}
<HelloWorld  :msg="showTecnologia ? tecnologia : 'Ain VueJs não presta, ainnnnn'"/>

<input type="text" v-model="user.firstName">
<h1>{{ user.firstName }}</h1>
<p>Nome completo: {{ fullName }}</p>
</template>

<script>
import { ref, computed, watch } from 'vue';

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
      this.user.lastName = "Maverick"
    }
  },
  setup() {
    
    let user = ref({
      firstName: "Welen",
      lastName: "Almeida"
    });

    const fullName = computed(() => {
        return `${user.value.firstName} ${user.value.lastName}`;
    });

    watch(() => user.value.lastName, () => {
      window.location.href = 'https://google.com';
    }, {
      deep: true
    });

    const framework = "VueJs";

    return {
      user,
      framework,
      fullName
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

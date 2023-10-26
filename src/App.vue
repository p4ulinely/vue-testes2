<template>
  <div>
    <p>APP</p>
    <hr>
    <PrimeiroComponente v-bind:msgPassada="msgPassada" v-bind:dados="dados" />
    <hr>
    <ContadorComponente />
    <hr>
    <FormComponente />
    <hr>
    <p>Todos os direitos reservados. {{ new Date().getFullYear() }} - {{ new Date(time1()) }}</p>
  </div>
</template>

<script>
  import PrimeiroComponente from './components/PrimeiroComponente.vue'
  import ContadorComponente from './components/ContadorComponente.vue';
  import FormComponente from './components/FormComponente.vue';

  export default {
    name: 'App',
    data() {
      return {
        nome: '',
        msgPassada: 'mensagem passada do componente App.vue',
        dados: {
          avatar: 'https://cdn-icons-png.flaticon.com/512/4645/4645949.png',
          nomeCompleto: 'Paulinely Morgan',
          idade: 34
        }
      }
    },
    components: {
      PrimeiroComponente,
      ContadorComponente,
      FormComponente
    },
    methods: {
      time1() {
        return Date.now()
      }
    },
    computed: {
      time2() {
        return Date.now()
      }
    }
  }
</script>
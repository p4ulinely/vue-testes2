<template>
  <div>
    <p>APP</p>
    <hr>
    <PrimeiroComponente v-bind:msgPassada="msgPassada" v-bind:dados="dados" />
    <hr>
    <ContadorComponente />
    <hr>
    <FormComponente v-on:dadosForm="mostraDadosVindoDoFilho"/>
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
      },
      mostraDadosVindoDoFilho(dados) {
        console.log('dados vindo do filho', dados);
      }
    },
    computed: {
      time2() {
        return Date.now()
      }
    }
  }
</script>
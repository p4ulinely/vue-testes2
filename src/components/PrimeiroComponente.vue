<template>
  <div>
    <p>PrimeiroComponente</p>
    <p>msg passada: {{ msgPassada }}</p>
    <div>
      <p>perfil: {{ perfil }}</p>
      <p><img v-bind:src="dados.avatar" alt="" height="40" width="40"></p>
      <p>nome completo: {{dados.nomeCompleto}}</p>
      <p>idade: {{dados.idade}}</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'PrimeiroComponente',
    data() {
      return {
        perfil: "perfil de usuário"
      }
    },
    props: {
      msgPassada: String,
      dados: Object
    }
  }
</script>

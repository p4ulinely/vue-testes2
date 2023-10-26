<template>
  <div>
    <h4>PrimeiroComponente</h4>
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
    props: { // tmb pode ser omitido o tipo e passado um array ['msgPassada', 'dados']
      msgPassada: String,
      dados: Object
    }
  }
</script>

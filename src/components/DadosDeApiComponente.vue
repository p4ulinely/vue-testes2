<template>
    <div>
        <h4>Dados vindo de resquest duma API</h4>
        <div v-if="!loading">{{ dados }}</div>
        <span v-else>Carregando dados...</span>
    </div>
</template>

<script>
    import axios from "axios";

    export default {
        name: 'DadosDeApiComponente',
        data() {
            return {
                loading: true,
                dados: {}
            }
        },
        mounted() {
            axios.get('https://api.coindesk.com/v1/bpi/currentprice.json')
                .then(res => {
                    this.dados = res.data.bpi;
                })
                .catch(ex => {
                    console.error(ex);
                })
                .finally(() => this.loading = false)
        }
    }
</script>
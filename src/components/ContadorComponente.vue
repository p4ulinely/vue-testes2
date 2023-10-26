<template>
    <div>
        contador: {{ count }}
        <input type="button" value="+" v-on:click="mais">
        <input type="button" value="-" @click="menos">
        <span>&nbsp;{{mudou}}</span>
    </div>
</template>

<script>
    export default {
        name: 'ContadorComponente',
        data() {
            return {
                count: 1,
                mudou: ''
            }
        },
        methods: {
            mais() {
                this.count++;
            },
            menos() {
                this.count--;
            }
        },
        watch: {
            count() {
                this.mudou = 'mudou...';
                setTimeout(() => this.mudou = "", 1000)
            }
        }
    }
</script>
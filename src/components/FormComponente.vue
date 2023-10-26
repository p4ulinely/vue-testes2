<template>
    <div>
        <h4>Fomulário</h4>
        <form id="meu-form">
            <p><input type="text" placeholder="nome" v-model="form.input_name"> {{form.input_name}}</p>
            <p><input type="text" placeholder="e-mail" v-model="form.input_email"> {{form.input_email}}</p>
            <input @click.prevent="submitForm" type="submit" value="Enviar">
        </form>
    </div>
</template>

<script>
    export default {
        name: 'FormComponente',
        data() {
            return {
                form: {
                    input_name: '',
                    input_email: ''
                }
            }
        },
        methods: {
            submitForm() {
                console.log('envia request pra uma api ou para componente pai...', this.form);
                this.$emit('dadosForm', this.form);
            }
        }
    }
</script>
<script>
export default {
    
    data() {
        return {
            dialogo: ' '
        }
    },
    methods: {
        enviar() {
            this.$emit('testa',this.dialogo)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot>
        <br>
        <textarea type="text" v-model="dialogo" class="form-input border-gray-300 p-5 my-5 rounded-md text-black" @input="enviar()"></textarea>

    </div>
</template>
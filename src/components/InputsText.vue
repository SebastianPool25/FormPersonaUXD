<script>
export default {
    
    data() {
        return {
            dialogo: ' '
        }
    },
    methods: {
        enviar() {
            this.$emit('data',this.dialogo)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot>
        <br>
        <input type="text" class="form-input border-gray-300 p-5 my-5 rounded-md text-black" v-model="dialogo" @change="enviar">

    </div>
</template>
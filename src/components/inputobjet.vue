<script>
export default{
    data(){
        return{
            obje:" ",
        }
    },
    props:{
        index:null
    },
    methods: {
        enviar() {
            obje: this.objetinfo,
            this.$emit('objetivo',this.dato, this.index)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot>
        <input type="text" v-model="obje" name="objetinfo" id="objetinfo" @input="enviar" class="form-input border-gray-300 p-5 my-5 rounded-md text-black">
    </div>
</template>
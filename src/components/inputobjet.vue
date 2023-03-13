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
            obje: this.elobjetivo,
            this.$emit('objetivo',this.obje, this.index)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot>
        <input type="text" v-model="obje" name="elobjetivo" id="elobjetivo" @input="enviar" class=" border-gray-300 p-5 my-5 rounded-md text-black">
    </div>
</template>
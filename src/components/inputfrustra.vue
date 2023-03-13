<script>
export default{
    data(){
        return{
            frus:" ",
        }
    },
    props:{
        index:null
    },
    methods: {
        enviar() {
            frus: this.frustra,
            this.$emit('frustracion',this.frus, this.index)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot>
        <input type="text" v-model="frus" name="frustra" id="frustra" @input="enviar" class=" border-gray-300 p-5 my-5 rounded-md text-black">
    </div>
</template>
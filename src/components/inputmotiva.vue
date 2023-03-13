<script>
export default{
    data(){
        return{
            frase:'',
            porcentaje:" ",
        }
    },
    props:{index:null},
    
    methods:{
        enviar(){
            frase: this.motivacion
            porcentaje: this.porcen
            this.$emit('motivaciones',this.frase,this.porcentaje,this.index)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot>
        <input type="text" v-model="frase" name="motivacion" id="motivacion" @input="enviar" class="form-input border-gray-300 p-5 my-5 rounded-md text-black">
        <input type="range" min="0" max="100" v-model="porcentaje" name="porcen" id="porcen" @input="enviar">
    </div>
</template>
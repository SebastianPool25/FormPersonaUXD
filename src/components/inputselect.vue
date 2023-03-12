<script>
export default {
    
    data() {
        return {
            value: 0
        }
    },
    props: {
    Datos: Object
    },
    methods: {
        enviar() {
            this.$emit('valor',this.value)
        }
    }
    
}

</script>

<template>
    <div>
        <slot ></slot> 
        
        <select  v-model="value" @change="enviar" class="form-input border-gray-300 p-5 my-5 rounded-md text-black">
                            <option value="1">{{ Datos.Uno }}</option>
                            <option value="2">{{ Datos.Dos }}</option>
                            <option value="3">{{ Datos.Tres }}</option>
                            <option value="4">{{ Datos.Cuatro }}</option>
                            <option value="5">{{ Datos.Cinco }}</option>
                            <option value="6">{{ Datos.Seis }}</option>
        </select>
    </div>
</template>
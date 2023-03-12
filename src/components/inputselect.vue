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
                            <option value="1">Soltero</option>
                            <option value="2">Casado</option>
                            <option value="3">Divorciado</option>
                            <option value="4">Separado</option>
                            <option value="5">Union libre</option>
                            <option value="6">Viudo</option>
                            

        </select>
    </div>
</template>
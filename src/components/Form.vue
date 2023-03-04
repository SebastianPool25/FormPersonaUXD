<script>
import boton from '../components/buttsSubmit.vue'

import axios from 'axios';
export default {
  components:{
    boton
  },
    data() {
        return {
            Nombre: " ",
            Edad: " ",
            EstadoCivil: " ",
            Trabajo:" ",
            Residencia: " ",
            Cita: " ",
            CitaAutor: " ",
            Bio: " ",
            Personalidad1: " ",
            Personalidad2:" ",
            Personalidad3: " ",
            Personalidad4: " ",
            Objetivos: " ",
            Frustraciones: [],
            Motivaciones: [],
            Marcas: " ",
        };
    },
    mounted() {
        

    },
    methods: {
        Enviar(){
            axios.post("/api/guardarPersonasUxd.php", {
                nombre: this.Nombre,
                edad: this.Edad,
                estadoCivil: this.EstadoCivil,
                trabajo: this.Trabajo,
                residencia: this.Residencia,
                cita: this.Cita,
                citaAutor: this.CitaAutor,
                bio: this.Bio,
                personalidad01: this.Personalidad1,
                personalidad02: this.Personalidad2,
                personalidad03: this.Personalidad3,
                personalidad04: this.Personalidad4,
                objetivos: this.Objetivos,
                frustraciones: this.Frustraciones,
                motivaciones: this.Motivaciones,
                marcas: this.Marcas
                //completar las variables, estas deben llamarse como las que se recibirán en el backend sin el símbolo del dolar $
            })
            .then((response) => {
            console.log(response.status)
            });


        }

    }
}




</script>

<template>
  <body class="bg-blue-300 font-mono flex">
  <div class="p-5 mx-5">
  <h1 class="my-5 text-xl">Llena el Formulario de sus datos personales</h1>
  <div id="app">
  <form>
    <div class="pl-5 grid gap-5  grid-cols-3 bg-blue-300">
    <div class="my-5">
    <label for="nombre" class="text-lg">Nombre</label><br>
    <input type="text" id="nombre" v-model="Nombre" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingresa nombre">
    </div>
    <div class="my-5">
    <label for="edad" class="text-lg">Edad</label><br>
    <input type="int" id="edad" v-model="Edad" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingresa edad">
    </div>
    <div class="my-5">
    <label for="estadoCivil" class="text-lg">Estado Civil</label><br>
    <select name="estadoCivil" id="estadoCivil" v-model="EstadoCivil" class="form-input border-gray-300 p-2 rounded-md text-black">
    <option>Soltero</option>
    <option>Casado</option>
    <option>Divorciado</option>
    <option>Divorciado</option>
    <option>Separado</option>
    <option>Union Libre</option>
    <option>Viudo</option>
    </select>
    </div>
    <div class="my-5">
    <label for="trabajo" class="text-lg">Trabajo</label><br>
    <input type="text" id="trabajo" v-model="Trabajo" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese su trabajo">
    </div>
    </div>
    <h1 class="my-5 text-xl">Datos de personalidad</h1>
    <div class="pl-5 grid gap-6 grid-cols-3 bg-blue-300">
    <div class="my-5">
    <label for="cita" class="text-md">Escribe una cita</label><br>
    <input type="text" id="cita" v-model="Cita" class="form-input border-gray-300 p-2 rounded-md text-black h-full w-full" placeholder="Ingrese una cita">
    </div>
    <div class="my-5">
    <label for="citaAutor" class="text-lg">Autor de la cita</label><br>
    <input type="text" id="citaAutor" v-model="CitaAutor" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese autor">
    </div>
    <div class="my-5">
    <label for="bio" class="text-lg">Escribe tu bio</label><br>
    <input type="text" id="bio" v-model="Bio" class="form-input border-gray-300 p-2 rounded-md text-black h-full w-full" placeholder="Ingrese tu bio">
    </div>
    <div class="my-5">
    <label for="personalidad01" class="text-lg">Porcentaje de personaliad 1</label><br>
    <input type="int" id="personalidad01" v-model="Personalidad1" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese porcentaje">
    </div>
    <div class="my-5">
    <label for="personalidad02" class="text-lg">Porcentaje de personaliad 2</label><br>
    <input type="int" id="personalidad02" v-model="Personalidad2" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese porcentaje">
    </div>
    <div class="my-5">
    <label for="personalidad03" class="text-lg">Porcentaje de personaliad 3</label><br>
    <input type="int" id="personalidad03" v-model="Personalidad3" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese porcentaje">
    </div>
    <div class="my-5">
    <label for="personalidad04" class="text-lg">Porcentaje de personaliad 4</label><br>
    <input type="int" id="personalidad04" v-model="Personalidad4" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese porcentaje">
    </div>
    <div class="my-5">
    <label for="Objetivos" class="text-lg">Objetivos</label><br>
    <input type="text" id="Objetivos" v-model="Objetivos" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese Objetivos">
    </div>
    <div class="my-5">
    <label for="Frustraciones" class="text-lg">Frustraciones</label><br>
    <input type="texr" id="Frustaciones" v-model="Frustraciones" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese Frustraciones">
    </div>
    <div class="my-5">
    <label for="Motivaciones" class="text-lg">Motivaciones</label><br>
    <input type="text" id="Motivaciones" v-model="Motivaciones" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese Motivaciones">
    </div>
    <div class="my-5">
    <label for="Marcas" class="text-lg">Marcas</label><br>
    <input type="text" id="Marcas" v-model="Marcas" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese sus marcas">
    </div>
    </div>

    <div>
    <boton :desactivar="true" @click="Enviar()">Registrar</boton>
    </div>
    
  </form>
</div>
  </div>
</body>
</template>
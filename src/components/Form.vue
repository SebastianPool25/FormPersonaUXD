<script>
import boton from '../components/buttsSubmit.vue';
import slider from '../components/InputSlider.vue';
import caja from '../components/InputsText.vue';
import cajagrande from '../components/textarea.vue'

import axios from 'axios';
export default {
  components:{
    boton,slider,caja,cajagrande
  },
  emits: ['person','data','testa'],
    data() {
        return {
            Nombre: " ",
            Edad: "",
            EstadoCivil: " ",
            Trabajo:" ",
            Residencia: " ",
            Cita: " ",
            CitaAutor: " ",
            Bio: " ",
            Personali01: 50,
            Personali02: 50,
            Personali03: 50,
            Personali04: 50,
            Objetivos: " ",
            Frustraciones: [],
            Motivaciones: [],
            Marcas: " ",
            Soltero: 1,
        };
    },
    mounted() {
        

    },
    methods: {
      nombreyapellido(s){
this.Nombre=s;
      },
      viejo(s){
  this.Edad=s;
      },
      chamba(s){
this.Trabajo=s;
      },
      pueblito(s){
this.Residencia=s;
      },
      inspira(s){
this.Cita=s;
      },
      creador(s){
this.CitaAutor=s;
      },
      biografia(s){
this.Bio=s;
      },
        perso1(s){
  this.Personali01=s;
        },
        perso2(s){
  this.Personali02=s;
        },
        perso3(s){
  this.Personali03=s;
        },
        perso4(s){
  this.Personali04=s;
        },
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
                personalidad01: this.Personali01,
                personalidad02: this.Personali02,
                personalidad03: this.Personali03,
                personalidad04: this.Personali04,
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
  <body class="bg-blue-300 font-mono flex xl:font-bold">
  <div class="p-5 mx-5">
  <h1 class="my-5 text-xl">Llena el Formulario de sus datos personales</h1>
  <div id="app">
  <form>
    <div class="pl-5 grid gap-5 grid-cols-3 bg-blue-300 text-center max-lg:grid-cols-1">
    <div class="my-5">
    <label for="nombre" class="text-lg">Nombre</label><br>
    <caja @data="nombreyapellido"></caja>
    </div>
    <div class="my-5">
    <label for="edad" class="text-lg">Edad</label><br>
    <caja @data="viejo"></caja>
    </div>
    <div class="my-5">
    <label for="estadoCvil" class="text-lg">Estado Civil</label><br>
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
    <caja @data="chamba"></caja>
    </div>
    <div class="my-5">
    <label for="Residencia" class="text-lg">Residencia</label><br>
    <caja @data="pueblito"></caja>
    </div>
    </div>
    <h1 class="my-5 text-xl">Datos de personalidad</h1>
    <div class="pl-5 bg-blue-300 text-center my-10 grid grid-cols-3 gap-4 max-lg:grid-cols-1">    
    <div class="my-10">
    <label for="cita" class="text-lg">Escribe una cita</label><br>

    <cajagrande @testa="inspira"></cajagrande>

    <label for="citaAutor" class="text-lg">Autor de la cita</label><br>
    <caja @data="creador"></caja>
    </div>
    <div class="my-10">
    <label for="bio" class="text-lg">Escribe tu bio</label><br>
    <cajagrande @testa="biografia"></cajagrande>
    </div>

    <div class="my-10 max-lg:grid-cols-1">
    <slider @perso="perso1">Personalidad 01</slider>
    <br>
    <slider @person="perso2">Personalidad 02</slider>
    <br>
    <slider @person="perso3">Personalidad 03</slider>
    <br>
    <slider @person="perso4">Personalidad 02</slider>
    </div>
    <div class="mt-10">
    <div class="mt-10 grid grid-cols-3 gap-4">
    <label for="Objetivos" class="text-lg">Objetivos</label><br>
    <input type="text" id="Objetivos" v-model="Objetivos" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese Objetivos">
    <label for="Frustraciones" class="text-lg">Frustraciones</label><br>
    <input type="text" id="Frustaciones" v-model="Frustraciones" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese Frustraciones">
    <label for="Motivaciones" class="text-lg">Motivaciones</label><br>
    <input type="text" id="Motivaciones" v-model="Motivaciones" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese Motivaciones">
    <label for="Marcas" class="text-lg">Marcas</label><br>
    <input type="text" id="Marcas" v-model="Marcas" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese sus marcas">
    </div>
  </div>
    
    </div>

    <div>
    <boton type="button" @click="Enviar()">Registrar</boton>
    </div>
    
  </form>
</div>
  </div>
</body>
</template>
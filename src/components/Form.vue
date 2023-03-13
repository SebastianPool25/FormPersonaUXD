<script>
import boton from '../components/buttsSubmit.vue';
import slider from '../components/InputSlider.vue';
import caja from '../components/InputsText.vue';
import cajagrande from '../components/textarea.vue';
import sel from '../components/inputselect.vue';
import objetivo from '../components/inputobjet.vue'
import frustra from '../components/inputfrustra.vue'
import motivacion from '../components/inputmotiva.vue'

import axios from 'axios';
export default {
  components:{
    boton,slider,caja,cajagrande,sel,objetivo, motivacion, frustra
  },
  emits: ['person','valor','data','testa','objetivo','motivaciones','frustracion'],
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
            Personali01: 50,
            Personali02: 50,
            Personali03: 50,
            Personali04: 50,
            nuevosobjetivos:'',
            Objetivos: [{value:''}],
            nuevasfrustraciones:'',
            Frustraciones: [{value:''}],
            nuevasmotivaciones:'',
            Motivaciones: [{value: '','porcentaje':''}],
            Marcas: " ",
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
      Select(s){
this.EstadoCivil=s;
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
        marca(s){
  this.Marcas=s;
        },
        masobjetivos(s, index){
      this.Objetivos[index] = {value: s}
    },
    masfrustraciones(s, index){
      this.Frustraciones[index] = {value: s}
    },
    masmotivos(f,p, index){
      this.Motivaciones[index] = {value: f,porcentaje: p}
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
  <body class="bg-white font-mono flex justify-center xl:font-bold">
  <div class="p-5 mx-5 bg-white">
  <div id="app">
  <form>
      <h1 class="my-5 text-xl p-5">Llena el Formulario de sus datos personales</h1>
    <div class="pl-5 grid gap-5 grid-cols-3 bg-blue-300 text-center rounded-xl max-lg:grid-cols-1">  
    <div class="my-5">
    <label for="nombre" class="text-lg">Nombre</label><br>
    <p v-if="Nombre == '' " class="text-red-800 text-lg"> Ingresa su nombre, plis :(</p>
    <caja @data="nombreyapellido"></caja>
    </div>
    <div class="my-5">
    <label for="edad" class="text-lg">Edad</label><br>
    <p v-if="Edad >=100" class="text-red-800"> la edad es invalida</p>
    <p v-if="Edad == '' " class="text-red-800"> Ingrese su edad, plis :(</p>
    <caja @data="viejo"></caja>
    </div>
    <div class="my-5">
    <label for="estadoCvil" class="text-lg">Estado Civil</label><br>
    <sel @valor="Select" :Datos='{"Uno": "Soltero","Dos": "Casado","Tres": "Divorciado","Cuatro": "Separado","Cinco": "Union libre","Seis": "Viudo"} '></sel>
    </div>
    <div class="my-5">
    <label for="trabajo" class="text-lg">Trabajo</label><br>
    <p v-if="Trabajo == '' " class="text-red-800"> Ingrese su trabajo, plis :(</p> 
    <caja @data="chamba"></caja>
    </div>
    <div class="my-5">
    <label for="Residencia" class="text-lg">Residencia</label><br>
    <p v-if="Residencia == '' " class="text-red-800"> Ingrese su pueblito, plis :(</p>
    <caja @data="pueblito"></caja>
    </div>
    </div>
    <h1 class="my-5 text-xl p-5">Datos de personalidad</h1>
    <div class="pl-5 bg-blue-300 text-center my-10 grid grid-cols-3 gap-4 rounded-xl max-lg:grid-cols-1">    
    <div class="my-10">
    <label for="cita" class="text-lg">Escribe una cita</label><br>
    <p v-if="Cita == '' " class="text-red-800"> Ingrese una cita, plis :(</p>
    <cajagrande @testa="inspira"></cajagrande>

    <label for="citaAutor" class="text-lg">Autor de la cita</label><br>
    <p v-if="CitaAutor == '' " class="text-red-800"> Ingrese el autor, plis</p>
    <caja @data="creador"></caja>
    </div>
    <div class="my-10">
    <label for="bio" class="text-lg">Escribe tu bio</label><br>
    <p v-if="Bio == '' " class="text-red-800"> Ingrese su bio, plis :(</p>
    <cajagrande @testa="biografia"></cajagrande>
    </div>

    <div class="my-10 max-lg:grid-cols-1">
    <slider @person="perso1">Personalidad 01</slider>
    <br>
    <slider @person="perso2">Personalidad 02</slider>
    <br>
    <slider @person="perso3">Personalidad 03</slider>
    <br>
    <slider @person="perso4">Personalidad 02</slider>
    </div>
  </div>

    <div class="mt-10">
      <div>
      <h1 class="my-5 text-xl">Datos de persona</h1>
      <div class="mt-10 grid grid-cols-4 gap-5 bg-blue-300 rounded-xl max-lg:grid-cols-1">
<div class="mx-10 p-5">
                <label for="objetivos" class="text-xl"> Objetivos: </label> 
                <div v-for="(obj, index) in Objetivos">
                  <objetivo @objetivo="masobjetivos" :index="index"> </objetivo>
     </div>
     <button v-on:click.prevent="this.Objetivos.push(nuevosobjetivos)" class="px-4 py-2 mb-2 bg-gray-600 text-white rounded"> Agregar</button>
</div>
<div class="mx-10 p-5">
               <label for="frustraciones" class="text-xl"> Frustraciones: </label> 
                <div v-for="(obj, index) in Frustraciones">
                  <frustra @frustracion="masfrustraciones" :index="index"></frustra>
                </div>
                <button v-on:click.prevent="this.Frustraciones.push(nuevasfrustraciones)" class="px-4 py-2 mb-2 bg-gray-600 text-white rounded"> Agregar</button> 
            </div>
<div class="mx-10 p-5">
                <label for="motivaciones" class="text-xl"> Motivaciones: </label> 
                <div v-for="(obj, index) in Motivaciones">
                  <motivacion @motivaciones="masmotivos" :index="index"></motivacion>
                
                </div>
                <button v-on:click.prevent="this.Motivaciones.push(nuevasmotivaciones)" class="px-4 py-2 mb-2 bg-gray-600 text-white rounded"> Agregar</button>
              </div>

<div class="mx-10 p-5">
    <label for="Marcas" class="text-xl">Marcas</label><br>
    <p v-if="marca == '' " class="text-red-800"> Ingrese su marca, plis :(</p>
    <caja @data="marca"></caja>
</div>
    </div>
</div>
    </div>

    

    <div class="flex justify-center">
    <boton @click="Enviar()" type="button">Registrar</boton>
    </div>
    
  </form>
</div>
  </div>
</body>
</template>
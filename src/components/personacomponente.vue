<script>
import axios from 'axios'
let API_URL = '/api/getPersonasUxd.php'

export default {

  data() {
    return {
        //variables de retorno  
        //para lista de personas
        personas: [],
        info:[],
      }
    },
    mounted() {
      axios
        .get(API_URL)
          .then((response) => {
          //paginas
          console.log (response.data.personas);
          this.info = response.data.info;
          this.personas = response.data.personas;
          
          console.log (this.personas)
          console.log(this.info)
      })
  },
}

</script>

<template>
  <body class="font-mono flex justify-center">
      <div>
        <div class="p-10 bg-blue-200"  v-for="(p) in personas">
          <div class="grid my-5 mx-8 gap-5 grid-cols-2 max-lg:grid-cols-1">
          <div class="bg-white rounded-xl my-5 mx-8">
            <h1 class="text-2xl p-5">Datos personales:</h1>
            <h2 class="text-lg p-5">Nombre: <br> <p class="font-bold">{{ p.nombre }}</p></h2>
            <h2 class="text-xl p-5">Edad:<br> <p class="font-bold">{{ p.edad }}</p></h2>
            <h2 class="text-xl p-5">Estado Civil:<br> <p class="font-bold">{{ p.estadoCivil }}</p></h2>
            <h2 class="text-xl p-5">Trabajo:<br> <p class="font-bold">{{ p.trabajo }}</p></h2>
            <h2 class="text-xl p-5">Residencia: <br> <p class="font-bold">{{ p.residencia }}</p></h2>
          </div>
          <div class="bg-white my-5 mx-8 text-lg p-5 rounded-xl">
            <h1 class="text-2xl">Datos de persona</h1>
            <ul class="my-5">Objetivos:
              <li></li>
            </ul>
            <ul class="my-5">Frustaciones:
              <li></li>
            </ul>
            <ul class="my-5">Motivaciones:
              <li></li>
            </ul>
            <ul class="my-5">Marcas:
              <li></li>
            </ul>
          </div>
          </div>
          <div class="bg-white my-5 mx-8 rounded-xl">
            <h1 class="text-2xl p-5">Datos de personsalidad:</h1>
            <div class="grid gap-5 grid-cols-3 max-lg:grid-cols-1">
            <div>
              <h2 class="text-lg p-5">Cita: <br><p class="font-bold">{{ p.cita }}</p></h2>
              <h2 class="text-lg p-5">Autor de la cita: <br><p class="font-bold">{{ p.citaAutor }}</p></h2>
            </div>
            <h2 class="text-md p-5">Bio: <br><p class="font-bold">{{ p.bio }}</p></h2>
            <div class="p-5 ml-5">
              <h2>Personalidad 1:</h2>
              <progress id="file" max="100" value="70"></progress> ({{ p.personalidad01}}%)
              <h2>Personalidad 2:</h2>
              <progress id="file" max="100" value="70"></progress> ({{ p.personalidad02}}%)
              <h2>Personalidad 3:</h2>
              <progress id="file" max="100" value="70"></progress> ({{ p.personalidad03}}%)
              <h2>Personalidad 4:</h2>
              <progress id="file" max="100" value="70"></progress> ({{ p.personalidad04}}%)
            </div>
          </div>
        </div>
        </div>
      </div>
  </body>
</template>

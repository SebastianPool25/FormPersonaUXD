<script>
import axios from 'axios'

let API_URL = '/api/getPersonasUxd.php'
export default {

  data() {
    return {
        contador:0,
        //variables de retorno  
        //para lista de personas
        personas: [],
        persona:[],
        infopersona:[],
        info:[],
      }
    },
    mounted() {
      axios
        .get('/api/getPersonasUxd.php')
          .then((response) => {
          //paginas
          console.log (response.data.personas);
          this.info = response.data.info;
          this.personas = response.data.personas;
          
          console.log (this.personas)
          console.log(this.info)
      })
  
    },
    methods: {
      jalarpesona(id){
        //url de consumo API
        API_URL = '/api/getPersonasUxd.php?id=' + id
            console.log(API_URL)
            //lo obtiene
            axios.get(API_URL)
                //
                .then((response) => {
                    console.log(response) //regresa datos de un solo personaje
                    //c
                    this.infopersona = response.data.persona;
                    console.log(this.infopersona)
                })
        },//Contiene el array de cada personaje con sus datos
    },
  }


</script>

<template>
  <body class="font-mono grid grid-cols-2 bg-blue-200">
    <div class="bg-white rounded-xl">
      <thead>
      <h1 class="text-xl">Lista de personas</h1>
      <tr>
        <th>
          <div>ID</div>
        </th>
        <th>Nombre</th>
      </tr>
    </thead>
    <tbody v-for="(p,contador) in personas">
      <tr>
        <td>
          <div class="ml-9">{{contador += 1}}</div>
        </td>
        <td>
          <div>
            <button @click="jalarpesona(p.id)">
              {{ p.nombre }}
            </button>
          </div>
        </td>
      </tr>
    </tbody>

    </div>
      <div>
        <div class="p-10 bg-blue-200 w-full">
          <div class="grid gap-5 grid-cols-2 max-lg:grid-cols-1">
            <div class="bg-white rounded-xl">
            <h1 class="text-2xl p-5">Datos personales:</h1>
            <h2 class="text-lg p-5">Nombre: <br>{{ infopersona.nombre }}</h2>
            <h2 class="text-xl p-5">Edad: <br>{{ infopersona.edad }}</h2>
            <h2 class="text-xl p-5">Estado Civil: <br>{{ infopersona.estadoCivil }}</h2>
            <h2 class="text-xl p-5">Trabajo: <br>{{ infopersona.trabajo }}</h2>
            <h2 class="text-xl p-5">Residencia: <br>{{ infopersona.residencia }}</h2>
          </div>
          <div class="bg-white text-lg p-5 rounded-xl">
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
          <div class="bg-white my-5 mx-8 rounded-xl w-full">
            <h1 class="text-2xl p-5">Datos de personsalidad:</h1>
            <div class="grid gap-5 grid-cols-2 max-lg:grid-cols-1">
            <div>
              <h2 class="text-lg p-5">Cita: <br>{{ infopersona.cita }}</h2>
              <h2 class="text-lg p-5">Autor de la cita: <br>{{ infopersona.citaAutor }}</h2>
            </div>
            <h2 class="text-md p-5">Bio: <br>{{ infopersona.bio }}</h2>
          </div>
          <div class="p-5 ml-5">
              <h2>Personalidad 1:</h2>
              <progress id="file" max="100" value="70"></progress>({{ infopersona.personalidad01 }}%)
              <h2>Personalidad 2:</h2>
              <progress id="file" max="100" value="70"></progress>({{ infopersona.personalidad02 }}%)
              <h2>Personalidad 3:</h2>
              <progress id="file" max="100" value="70"></progress>({{ infopersona.personalidad03 }}%)
              <h2>Personalidad 4:</h2>
              <progress id="file" max="100" value="70"></progress>({{ infopersona.personalidad04 }}%)
            </div>
        </div>
        </div>
      </div>

  </body>
</template>

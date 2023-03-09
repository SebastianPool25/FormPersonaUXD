<script>
import axios from 'axios'

let API_URL = 'http://isclab.com.mx/personasuxd/getPersonasUxd.php'

export default {

  data() {
    return {
      info: [],
      personajes: [],
      cont: 1,
      Busca: "",
      dato: "",
      detalle_personajes: []
    }
  },

  mounted() {
    axios.get(API_URL)
      .then((response) => {
        this.info = response.data.info;
        this.personajes = response.data.results;
      })
  },

  methods: {
    datosp(id) {
      API_URL='http://isclab.com.mx/personasuxd/getPersonasUxd.php'+id
      console.log(API_URL)
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.detalle_personajes = response.data;
        console.log(this.detalle_personajes)
      })
    } 
}
}


</script>

<template>
  <body class="bg-blue-200 font-mono grid grid-cols-2">
    <div class="p-5">
      <label for="buscador" class="font-bold">Buscador</label><br>
      <input type="text" class="form-input border-gray-300 p-5 my-5 rounded-md text-black">
      <div>
        <h2>Hay {{ info.count }} personajes en el programa de Rick & Morty</h2>
        <br>
        <ul class="pl-5">
          <li v-for="p in personajes">
            <button @click="datosp(p.id)" class="my-2">{{ p.name }}</button>
          </li>
        </ul>
      </div>
      </div>
      <div>
        <div class="p-10 bg-slate-400">
          <h1>Datos personales:</h1>
          <div class="bg-white my-5 mx-8">
            <h1>Datos personales:</h1>
            <h2>Nombre:</h2>
            <h2>Edad:</h2>
            <h2>Estado Civil:</h2>
            <h2>Trabajo:</h2>
            <h2>Residencia:</h2>
          </div>
          <h1>Datos de personsalidad:</h1>
          <div class="bg-red-200 grid gap-5 grid-cols-3 my-5 mx-8">
            <div>
              <h2>Cita:</h2>
              <h2>Autor de la cita:</h2>
            </div>
            <h2>Bio:</h2>
            <div>
              <h2>Personalidad 1:</h2>
              <progress id="file" max="100" value="70"></progress>
              <h2>Personalidad 2:</h2>
              <progress id="file" max="100" value="70"></progress>
              <h2>Personalidad 3:</h2>
              <progress id="file" max="100" value="70"></progress>
              <h2>Personalidad 4:</h2>
              <progress id="file" max="100" value="70"></progress>
            </div>
          </div>
          <h1>Datos de persona</h1>
          <div class="bg-purple-200 my-5 mx-8">
            <ul>Objetivos:
              <li></li>
            </ul>
            <ul>Frustaciones:
              <li></li>
            </ul>
            <ul>Motivaciones:
              <li></li>
            </ul>
            <ul>Marcas:
              <li></li>
            </ul>
          </div>

        </div>
      </div>
  </body>
</template>

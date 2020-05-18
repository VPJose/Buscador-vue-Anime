<template>
  <main>
    <div class="main">
      <buscador></buscador>
      <resultados :respuesta="respuesta" :nombre="nombre"></resultados>
    </div>
  </main>
</template>

<script>
// @ is an alias to /src
import jikanjs from 'jikanjs';
import Buscador from '../components/buscadorComponent'
import Resultados from '../components/resultadoComponent'

export default {
  components: {
    Buscador: Buscador,
    Resultados: Resultados
  },
  data() {
    return {
      respuesta: {
        anime: [],
        manga: [],
        person: []
      },
      nombre: {
        anime: false,
        manga: false,
        person: false
      }
    }
  },
  methods: {
    buscar() {
      jikanjs.loadTop('anime',1)
      .then((value) => { return value.top})
      .then((value) => {
        this.arreglo('anime',value,12);
        this.nombre.anime = true;
      })
      jikanjs.loadTop('manga',1)
      .then((value) => { return value.top})
      .then((value) => {
        this.arreglo('manga',value,12);
        this.nombre.manga = true;
      })
      jikanjs.loadTop('people',1)
      .then((value) => { return value.top})
      .then((value) => {
        this.arreglo('person',value,12);
        this.nombre.person = true;
      })
    },
    arreglo(tipo, valor, cantidad) {
      if (tipo == 'anime') {
        for (var i = 0; i < cantidad; i++) {
          this.respuesta.anime[i] = valor[i]
        }
      }
      if (tipo == 'manga') {
        for (var j = 0; j < cantidad; j++) {
          this.respuesta.manga[j] = valor[j]
        }
      }
      if (tipo == 'person') {
        for (var k = 0; k < cantidad; k++) {
          this.respuesta.person[k] = valor[k]
        }
      }
    }
  },
  created() {
    //do something after creating vue instance
    this.buscar();
  }

}
</script>

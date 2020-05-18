<template>
  <main>
    <div class="main">
      <buscador></buscador>
      <resultados :resultados="resultados" :dia="dia"></resultados>
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
      f: new Date(),
      diasSemana: new Array("sunday","monday","tuesday","wednesday","ththursday","friday","saturday"),
      dia: '',
      resultados: []
    }
  },
  created() {
    //do something after creating vue instance
    // console.log(this.diasSemana[this.f.getDay()]);
    this.dia = this.diasSemana[this.f.getDay()];
    console.log(this.dia);
    jikanjs.loadSchedule()
    .then(value => { return this.resultados = value })
    .catch(err => { console.log(err) })
  }
}
</script>

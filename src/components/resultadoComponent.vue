<template>
  <div id="resultado">
    <!-- <div class="img-search" id="respuesta">
      <img src="img/imgsearch.svg" alt="">
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing.</p>
    </div> -->
    <h2>{{dia}}</h2>
    <!-- <div v-for="result in resultado.diasSemana" :key="result.id">
      <div id="respuesta" class="contenedor-tarjeta">
      <div class="pantalla">
        <figure>
          <img :src="result.image_url" alt="" class="frontal">
          <h3 class="card-title-frontal">{{ result.title }}</h3>
          <h3 class="card-type result.type">{{ result.type }}</h3>
          <figcaption class="trasera">
            <div id="close" class="close">
              <span class="icon-cancel"></span>
            </div>
            <h3 class="card-title">{{ result.title }}</h3>
            <hr>
            <p>{{result.synopsis}}</p>
          </figcaption>
        </figure>
      </div>
    </div>
    </div> -->
  </div>
</template>

<script>
export default {
  props: ['resultados','dia'],
  data() {
    return {
      resultado: '',
    }
  },
  created() {
    //do something after creating vue instance
    this.resultado = this.resultados;
    console.log(this.resultados);
  }
}
</script>

<style lang="css" scoped>
</style>

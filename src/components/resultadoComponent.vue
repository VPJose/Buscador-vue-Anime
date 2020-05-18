<template>
  <div id="resultado">
    <!-- <div class="img-search" id="respuesta">
      <img src="img/imgsearch.svg" alt="">
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing.</p>
    </div> -->
    <div class="section" v-if="nombre.anime">
      <h3 class="title"> ANIME </h3>
      <div class="tarjeta">
        <div class="contenedor-tarjeta"  v-for="result in respuesta.anime" :key="result.id">
          <figure>
            <img :src="result.image_url" alt="" class="frontal">
            <h3 class="card-title-frontal">{{ result.title }}</h3>
            <h3 class="card-type" :class="result.type">{{ result.type }}</h3>
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
    </div>
    <div class="section" v-if="nombre.manga">
      <h3 class="title"> MANGA </h3>
      <div class="tarjeta">
        <div class="contenedor-tarjeta"  v-for="result in respuesta.manga" :key="result.id">
          <figure>
            <img :src="result.image_url" alt="" class="frontal">
            <h3 class="card-title-frontal">{{ result.title }}</h3>
            <h3 class="card-type" :class="result.type">{{ result.type }}</h3>
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
    </div>
    <div class="section" v-if="nombre.person">
      <h3 class="title"> PERSON </h3>
    <div class="tarjeta">
      <div class="contenedor-tarjeta"  v-for="result in respuesta.person" :key="result.id">
        <figure>
          <img :src="result.image_url" alt="" class="frontal">
          <h3 class="card-title-frontal">{{ result.title }}</h3>
          <h3 class="card-type" :class="result.type || 'TV'">{{ result.type || result.favorites}}</h3>
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
    </div>
  </div>
</template>

<script>
export default {
  props: ['respuesta','nombre'],
  data() {
    return {
    }
  },
  mounted() {
    //do something after creating vue instance

  }
}
</script>

<style lang="css" scoped>
</style>

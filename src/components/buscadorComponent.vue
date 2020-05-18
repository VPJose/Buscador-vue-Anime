<template>
  <div class="buscar">
    <form class="formulario-busqueda" id="formulario-busqueda">
    <div class="busqueda">
      <div class="busqueda-nombre">
        <input type="texto" name="nombre" value=""  v-model="busqueda.texto">
        <button type="submit" name="button" class="icon-search" @click.prevent="enviar"></button>
      </div>
      <div  class="select-busqueda">
        <select  v-model="busqueda.value">
          <option v-for="type in types" :key="type.id" :value="type.value">{{ type.texto }}
          </option>
        </select>
        <i></i>
      </div>
    </div>
    </form>
  </div>
</template>

<script>
import jikanjs from 'jikanjs';
export default {
  data() {
    return {
      types: [
        {
          value: 'tipo',
          texto : 'Tipo'
        },
        {
          value: 'anime',
          texto : 'Anime'
        },
        {
          value: 'manga',
          texto : 'Manga'
        },
        {
          value: 'music',
          texto : 'Music'
        },
        {
          value: 'Person',
          texto : 'Person'
        }
      ],
      busqueda: {
        value: 'tipo',
        texto : ''
      }
    }
  },
  methods: {
    enviar() {
      console.log(`${this.busqueda.value}: ${this.busqueda.texto}`);
      jikanjs.search(this.busqueda.value,this.busqueda.texto,1,['order_by=type'],30)
      .then(value => { console.log(value); })
    }
  }
}
</script>

<style lang="css" scoped>

</style>

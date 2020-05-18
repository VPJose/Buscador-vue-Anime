<template>
  <div class="menu-lateral" id="menu-lateral" @click.prevent="despalazarbarra($event.target)">
    <div class="contenedor menu-active">
      <div class="menu-logo">
        <a href="/">
          <h3> ListAnime </h3>
        </a>
      </div>
      <div class="menu-link">
        <a :href="link.href" v-for="link in links" :key="link.id">
          <span :class="link.class"></span>
          <p>{{ link.texto }}</p>
        </a>
      </div>
      <form class="menu-search" id="barra-formulario">
        <input type="text" class="search" placeholder="Search">
        <button type="submit" name="button" class="menu-boton icon-search" @click.prevent="enviar()"></button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  props: ['links'],
  data() {
    return {

    }
  },
  methods: {
    despalzar() {
      let pantalla = document.getElementById('menu-lateral');
      let barra_lateral = document.getElementById('menu-lateral').firstElementChild;

      setTimeout(() => {
        if (barra_lateral.className !== 'contenedor menu-active') {
          pantalla.classList.remove('menu-Lateral-active');
          barra_lateral.classList.add('menu-active');
        }
      },2000);
    },
    despalazarbarra(event) {
      if (event.className == 'menu-lateral menu-Lateral-active') {
        this.despalzar();
      }
    },
    enviar() {
      console.log('si');
    }
  }
}
</script>

<style lang="css" scoped>
</style>

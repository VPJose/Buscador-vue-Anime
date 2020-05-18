<template>
  <div class="menu-lateral" id="menu-lateral">
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
        <button type="submit" name="button" class="menu-boton icon-search"></button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          class: 'icon-home',
          texto: 'inicio',
          href: '/'
        },
        {
          class: 'icon-monitor',
          texto: 'Anime',
          href: '/anime'
        },
        {
          class: 'icon-book-open',
          texto: 'Manga',
          href: '/'
        },
        {
          class: 'icon-music',
          texto: 'Music',
          href: '/'
        },
        {
          class: 'icon-user',
          texto: 'Person',
          href: '/'
        },
        {
          class: '',
          texto: 'About',
          href: '/about'
        }
      ]
    }
  },
  methods: {
    despalzar() {
      this.pantalla = document.getElementById('menu-lateral');
      this.barra_lateral = document.getElementById('menu-lateral').firstElementChild;

      if (this.barra_lateral.className !== 'contenedor menu-active') {
        this.pantalla.classList.remove('menu-Lateral-active');
        this.barra_lateral.classList.add('menu-active');
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>

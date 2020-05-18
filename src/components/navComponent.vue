<template>
  <nav>
    <div class="nav">
      <div class="item-logo">
        <a href="/">
          <h3>
            ListAnime
          </h3>
        </a>
      </div>
      <div class="item-link">
        <a :href="link.href" v-for="link in links" :key="link.id">
          <span :class="link.class"></span>
          <p>{{ link.texto }}</p>
        </a>
      </div>
      <form class="item-search" id="nav-formulario">
        <input type="text" class="search" placeholder="Search">
        <button type="submit" name="button" class="search-boton icon-search"></button>
      </form>
      <div class="menu" id="barra-lateral" @click.prevent="despalzar">
        <span class="icon-menu"></span>
      </div>
    </div>
  </nav>
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
          href: '/'
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

      if (this.barra_lateral.className == 'contenedor menu-active') {
        this.pantalla.classList.add('menu-Lateral-active');
        this.barra_lateral.classList.remove('menu-active');
      } else {
        this.pantalla.classList.remove('menu-Lateral-active');
        this.barra_lateral.classList.add('menu-active');
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>

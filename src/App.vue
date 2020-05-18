<template>
  <div id="app" class="container">
    <Navegacion :links="links"></Navegacion>
    <Barra-lateral :links="links"></Barra-lateral>
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view/>
    <Footer></Footer>
  </div>
</template>

<script>
import Navegacion from './components/navComponent'
import BarraLateral from './components/barraLateralComponent'
import Footer from './components/footerComponent'

export default {
  components: {
    Navegacion: Navegacion,
    BarraLateral: BarraLateral,
    Footer: Footer
  },
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
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

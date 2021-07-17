<template>
  <v-app dark>

    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      
        <nuxt-link to="/"><v-img
        lazy-src="/LOGO.png"
        max-height="50"
        max-width="100"
        src="/LOGO.png"
        class="img"
        ></v-img></nuxt-link>
      <v-spacer />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <a href="https://www.instagram.com/gc.olliveira/" target="_blank" style="text-decoration:none">
        <v-btn
          icon
        >
          <v-icon>mdi-instagram</v-icon>
        </v-btn>
      </a>
      <a href="https://www.facebook.com/GlauberCO" target="_blank" style="text-decoration:none">
        <v-btn
          icon
        >
          <v-icon>mdi-facebook</v-icon>
        </v-btn>
      </a>

    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }} - CREATED BY: GLAUBER OLIVEIRA</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Início',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Produtos',
          to: '/produtos'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'LOJÃO DAS PROMOÇÕES'
    }
  }
}
</script>

<style>
.img{
  margin-right: 25px;
  margin-left: 25px;
}
</style>
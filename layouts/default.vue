<template>
  <div id="app">
    <nav-bar-home />
    <nuxt />
    <footer-bar />
  </div>
</template>

<script>
// @ is an alias to /src
import NavBarHome from '@/components/NavBarHome'
import FooterBar from '~/components/FooterBar.vue'

export default {
  name: 'App',
  components: {
    NavBarHome,
    FooterBar,
  },

  data() {
    return {
      darkMode: false,
      isActiveDrawer: false,
    }
  },

  mounted() {
    document.documentElement.classList.add('has-aside-left')
    document.documentElement.classList.add('has-aside-mobile-transition')
    document.documentElement.classList.add('has-navbar-fixed-top')
    document.documentElement.classList.remove('has-aside-expanded')
  },
  methods: {
    menuClick(item) {
      if (item.action && item.action === 'dark-mode-toggle') {
        this.$store.commit('darkModeToggle')
      }
    },
  },
}
</script>

<template>
  <div class="default-app">
    <app-nav-bar />
    <div class="container">
      <nuxt />
    </div>
    <app-footer />
  </div>
</template>

<script>
import AppNavBar from '~/components/AppNavBar.vue'
import AppFooter from '~/components/AppFooter.vue'

export default {
  components: {
    AppNavBar,
    AppFooter
  },
  head () {
    return {
      meta: [
        {
          hid: 'theme-color',
          name: 'theme-color',
          content: '#2c3e50'
        },
        {
          hid: 'author',
          name: 'author',
          content: 'Bradley Tim'
        },
        {
          hid: 'keywords',
          name: 'keywords',
          content: 'Premier League, EPL, Champions League, Europa League, Laliga'
        },
        {
          hid: 'msapplication-navbutton-color',
          name: 'msapplication-navbutton-color',
          content: '#2c3e50'
        },
        {
          hid: 'apple-mobile-web-app-status-bar-style',
          name: 'apple-mobile-web-app-status-bar-style',
          content: '#2c3e50'
        }
      ]
    }
  }
}
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  overflow-x: hidden;
  min-height: 100vh;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.default-app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

a {
  text-decoration: none;
  color: #444;
  cursor: pointer;
}

ul {
  list-style: none;
}

.container {
  width: 90%;
  min-height: 100%;
  margin: 0 auto;
}

.loading {
  width: 130px;
}

.loading-or-error {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>

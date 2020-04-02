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

input[type='text'] {
  display: block;
  width: 100%;
  padding: .75rem;
  border: 2px solid #777;
  border-radius: 2px;
}

input[type='text']:focus {
  border: 2px solid rgb(78, 211, 106);
}

input[type='text']::placeholder {
  font-size: 1rem;
  text-transform: capitalize;
  letter-spacing: 1px;
}

input[type='file'] {
  display: block;
  width: 100%;
  background: #2c3e50;
  color: #eee;
  border-radius: 2px;
}

.btn {
  border: 1px solid #777;
  border-radius: 2px;
  padding: .5rem 1.25rem;
  text-align: center;
  background: #2c3e50;
  color: #ccc;
  font-size: 1.15rem;
  font-weight: 700;
  transition: all 300ms ease;
}

.btn:hover {
  background: #fff;
  color: #2c3e50;
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

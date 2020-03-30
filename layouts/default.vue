<template>
  <div>
    <the-nav-bar />
    <div class="container">
      <nuxt />
    </div>
    <the-footer />
  </div>
</template>

<script>
import TheNavBar from '~/components/TheNavBar.vue'
import TheFooter from '~/components/TheFooter.vue'

export default {
  components: {
    TheNavBar,
    TheFooter
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
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
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

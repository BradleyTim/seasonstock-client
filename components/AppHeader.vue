<template>
  <header>
    <h2 class="container brand-name">
      <nuxt-link class="brand-name-link" to="/">
        SEASON
      </nuxt-link>
    </h2>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style scoped>
header {
  border-bottom: 1px solid #eee;
  box-shadow: 0 3px 3px 0 #eee;
  padding: 1rem 0;
  background: #2c3e50;
}

.brand-name {
  font-size: 1.65rem;
  font-weight: 400;
  text-align: center;
}

.brand-name-link {
  color: #eee;
}
</style>

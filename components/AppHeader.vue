<template>
  <header>
    <h2 class="brand-name">
      <nuxt-link to="/">
        Seasons
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
  padding: .5rem 0;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.brand-name {
  font-size: 2rem;
  font-weight: 400;
  text-align: center;
}
</style>

<template>
  <header>
    <nav class="container">
      <nuxt-link class="menu-item header-link" to="/about">
        <font-awesome-icon :icon="['fas', 'question-circle']" />
      </nuxt-link>
      <h2 class="brand-name">
        <nuxt-link class="brand-name-link" to="/">
          SEASON
        </nuxt-link>
      </h2>
      <nuxt-link class="menu-item header-link" to="/">
        <font-awesome-icon :icon="['fas', 'shopping-cart']" />
      </nuxt-link>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style scoped>
header {
  padding: .45rem 0;
  background: #2c3e50;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 5;
}

nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.brand-name {
  font-size: 1.65rem;
  font-weight: 400;
  text-align: center;
}

.brand-name-link, .header-link {
  color: #eee;
}
</style>

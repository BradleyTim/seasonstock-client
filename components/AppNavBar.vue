<template>
  <header>
    <nav class="container">
      <h2 class="brand-name">
        <nuxt-link to="/">
          Seasons
        </nuxt-link>
      </h2>
      <ul class="menu">
        <li>
          <nuxt-link class="menu-item" to="/">
            <font-awesome-icon :icon="['fas', 'home']" />
          </nuxt-link>
        </li>
        <li>
          <nuxt-link class="menu-item" to="/">
            <font-awesome-icon :icon="['fas', 'shopping-cart']" />
          </nuxt-link>
        </li>
        <li>
          <nuxt-link class="menu-item" to="/about">
            <font-awesome-icon :icon="['fas', 'question-circle']" />
          </nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'AppNavBar'
}
</script>

<style scoped>
header {
  border-bottom: 1px solid #eee;
  box-shadow: 0 3px 3px 0 #eee;
  padding: 1rem 0;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.menu {
  flex: 1;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.menu-item {
  margin-left: 1.5rem;
  font-size: 1.25rem;
}

.brand-name {
  flex: 2;
  font-size: 2rem;
  font-weight: 900;
}
</style>

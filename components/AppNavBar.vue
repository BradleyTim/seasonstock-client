<template>
  <header>
    <nav class="container">
      <h2 class="brand-name">
        <nuxt-link class="nav-link" to="/">
          Seasons
        </nuxt-link>
      </h2>
      <ul class="menu">
        <li>
          <nuxt-link class="menu-item nav-link" to="/">
            <font-awesome-icon :icon="['fas', 'shopping-cart']" />
          </nuxt-link>
        </li>
        <li>
          <nuxt-link class="menu-item nav-link" to="/about">
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
  padding: .35rem 0;
  background: #2c3e50;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 5;
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

.nav-link {
  color: #eee;
}
</style>

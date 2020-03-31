<template>
  <header>
    <nav class="container">
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
  name: 'AppMobileNavBar'
}
</script>

<style scoped>
header {
  border-top: 1px solid #eee;
  box-shadow: 0 -5px -4px 0 #eee;
  padding: 1rem 0;

  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background: #fff;
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
  justify-content: space-around;
  align-items: center;
}

.menu-item {
  margin-left: 1rem;
  font-size: 1.5rem;
}

</style>

<template>
  <header>
    <nav class="container">
      <ul class="menu">
        <li>
          <nuxt-link class="menu-item" to="/">
            <font-awesome-icon :icon="['fas', 'home']" />
            <div>
              Home
            </div>
          </nuxt-link>
        </li>
        <li>
          <nuxt-link class="menu-item" to="/">
            <font-awesome-icon :icon="['fas', 'shopping-cart']" />
            <div>
              Cart
            </div>
          </nuxt-link>
        </li>
        <li>
          <nuxt-link class="menu-item" to="/about">
            <font-awesome-icon :icon="['fas', 'question-circle']" />
            <div>
              About
            </div>
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
  padding: .5rem 0;
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background: #2c3e50;
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
  text-align: center;
}

.menu-item {
  margin-left: 1rem;
  font-size: 1.5rem;
  color: #eee;
}

div {
  font-size: .7rem;
  margin-left: 1.15rem;
  font-weight: 100;
  /* text-align: center; */
}

</style>

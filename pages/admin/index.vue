<template>
  <section>
    <div class="title">{{ title }}</div>
    <nuxt-link class="btn btn-add-jersey" to="/admin/add-jersey">
      New Jersey
    </nuxt-link>
  </section>
</template>

<script>
export default {
  data () {
    return {
      title: 'ADMIN | DASHBOARD'
    }
  }
}
</script>

<style scoped>
section {
  margin: 4rem 0;
}

.title {
  color: #2c3e50;
  font-size: 1.35rem;
  font-weight: 700;
  letter-spacing: 1px;
}

div {
  color: red;
}

.btn-add-jersey {
  margin: 1rem 0;
}
</style>

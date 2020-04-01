<template>
  <section>
    <div>{{ title }}</div>
    <nuxt-link class="btn" to="/admin/add-jersey">
      New Jersey
    </nuxt-link>
  </section>
</template>

<script>
export default {
  data () {
    return {
      title: 'ADMIN'
    }
  }
}
</script>

<style scoped>
section {
  margin: 4rem 0;
}

div {
  color: red;
}

.btn {
  display: inline-block;
  margin-top: 1rem;
  border: 1px solid #eee;
  padding: .25rem 1rem;
}
</style>

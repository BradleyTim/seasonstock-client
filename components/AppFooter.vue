<template>
  <footer>
    <div class="container">
      <p class="copyright">
        &copy; Seasons Inc. All Rights Reserved.
      </p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'AppFooter'
}
</script>

<style scoped>
footer {
  border-top: 1px solid #eee;
  margin-top: auto;
  /* box-shadow: 2px -3px 0 0 #eee; */
  padding: 1rem 0;
}

.copyright {
  font-size: 1rem;
  color: #444;
  text-align: center;
}
</style>

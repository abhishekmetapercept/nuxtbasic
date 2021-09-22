<template>
  <div>
    <h1 style="color: red;">Hello World!</h1>
    <p>
      This page is rendered on the <strong>{{ rendering }}</strong>
    </p>
    <p v-if="rendering === 'server'">
      First  refresh is done on server side.
    </p>
    <p v-if="rendering === 'client'">Navigation is done on client side.</p>
    <ul>
      <li>Refresh the page for server page.</li>
      <li>Click the links to see client page.</li>
    </ul>

    <NuxtLink to="/about">About Page</NuxtLink>
  </div>
</template>
<script>
export default {
  asyncData () {
    return {
      rendering: process.server ? 'serverpage' : 'clientpage'
    }
  }
}
</script>

<style scoped>
p {
color: brown;
}
ul {
color: grey;}
</style>

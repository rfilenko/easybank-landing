<template>
  <main>
    <div class="error">
      <h1 v-if="error.statusCode === 404">Page not found</h1>
      <h1 v-else>An error occurred</h1>
      <nuxt-link to="/">Home page</nuxt-link>
    </div>
  </main>
</template>

<script>
export default {
  props: ["error"]
};
</script>
<style >
.error {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 85vh;
}
.error h1 {
  font-size: 2.25rem;
}
.error a {
  color: var(--accent-clr);
  text-decoration: underline;
  text-decoration-style: double;
  text-decoration-skip-ink: none;
}
</style>
<template>
  <div class="app">
    <AppHeader />
    <nuxt />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "~/components/AppHeader.vue";
import AppFooter from "~/components/AppFooter.vue";

export default {
  components: {
    AppHeader,
    AppFooter
  }
};
</script>
<style>
:root {
  --primary-clr: hsl(136, 65%, 51%);
  --secondary-clr: hsl(233, 26%, 24%);
  --accent-clr: hsl(192, 70%, 51%);
  --white-clr: hsl(0, 0%, 100%);
  --black-clr: #000000;
  --grayishBlue-clr: hsl(233, 8%, 62%);
  --lightGrayishBlue-clr: hsl(220, 16%, 96%);
  --veryLightGray-clr: hsl(0, 0%, 98%);
}
html {
  font-family: "Public Sans", sans-serif;
  font-size: 18px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

body {
  background: hsl(220, 16%, 96%);
  font-size: 18px;
  color: hsl(233, 26%, 24%);
}
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
.container {
  margin: 0 auto;
  text-align: center;
  margin-top: 2rem;
}
.btn {
  background: linear-gradient(to right, var(--primary-clr), var(--accent-clr));
  border: none;
  border-radius: 20px;
  padding: 0.5rem 1.25rem;
  color: var(--white-clr);
  white-space: nowrap;
  cursor: pointer;
}
.btn:hover {
  opacity: 0.89;
  background: linear-gradient(to right, var(--accent-clr), var(--primary-clr));
}
a {
  transition: all 0.2s ease;
}
a:focus {
  outline-style: dotted;
  outline-color: var(--accent-clr);
  outline-width: 2px;
  outline-offset: 2px;
}

@media screen and (max-width: 600px) {
  .container {
    padding: 0 20px;
  }
}
</style>

<template>
  <header>
    <div class="container">
      <div class="logo">
        <img src="../assets/images/logo.svg" alt="company logo" />
      </div>
      <nav>
        <ul>
          <li>
            <nuxt-link to="/">Home</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/about">About</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/contact">Contact</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/blog">Blog</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/careers">Careers</nuxt-link>
          </li>
        </ul>
      </nav>
      <div class="invite">
        <a class="btn" href="/">Request Invite</a>
      </div>
    </div>
  </header>
</template>

<style>
header {
  width: 100%;
  background: var(--white-clr);
  padding: 1rem;
}
header .invite {
  margin-left: auto;
  flex-basis: auto;
}
nav {
  margin: 0 auto;
}
ul {
  display: flex;
}
li {
  color: var(--grayishBlue-clr);
  font-size: 0.875rem;
  margin: 0 0.5rem;
}
@media screen and (max-width: 600px) {
  header .container,
  ul {
    flex-direction: column;
  }
  header .invite {
    margin: 1rem auto;
  }
}
</style>

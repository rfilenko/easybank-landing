<template>
  <header>
    <div class="container flex-col md:flex-row">
      <div class="logo self-center">
        <nuxt-link to="/">
          <img src="../assets/images/logo.svg" alt="company logo" />
        </nuxt-link>
      </div>
      <nav class="mx-auto">
        <ul class="flex flex-col md:flex-row">
          <li>
            <nuxt-link to="/" class="mx-2">Home</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/about" class="mx-2">About</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/contact" class="mx-2">Contact</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/blog" class="mx-2">Blog</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/careers" class="mx-2">Careers</nuxt-link>
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
  padding: 0.75rem 1rem;
  z-index: 10;
}
header .logo {
  transform: perspective(1px) translateZ(0);
}
header .logo:hover,
header .logo:focus,
header .logo:active {
  animation: logo-hover 1s ease-in-out 1;
}

@keyframes logo-hover {
  16.65% {
    transform: translateY(8px);
  }
  33.3% {
    transform: translateY(-6px);
  }
  49.95% {
    transform: translateY(4px);
  }
  66.6% {
    transform: translateY(-2px);
  }
  83.25% {
    transform: translateY(1px);
  }
  100% {
    transform: translateY(0);
  }
}

header .invite {
  flex-basis: auto;
}

nav li {
  color: var(--grayishBlue-clr);
  font-size: 0.875rem;
}
nav li {
  position: relative;
}
nav li a:hover {
  color: var(--secondary-clr);
}
@media screen and (min-width: 1024px) {
  nav li:hover:after {
    content: "";
    position: absolute;
    bottom: -1.35rem;
    left: 0;
    width: 100%;
    height: 4px;
    background: linear-gradient(
      to right,
      var(--primary-clr),
      var(--accent-clr)
    );
  }
}
@media screen and (max-width: 600px) {
  header .container,
  header .logo {
    margin-bottom: 1rem;
  }
  header .invite {
    margin: 1rem auto;
  }
}
</style>

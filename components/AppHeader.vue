<template>
  <header>
    <div class="container flex-col md:flex-row">
      <div class="logo w-full md:w-auto flex justify-between self-center">
        <nuxt-link to="/">
          <img src="../assets/images/logo.svg" alt="company logo" />
        </nuxt-link>
        <div class="hamburger-menu md:hidden" @click="toggleMenu">
          <img v-if="menuVisible" src="../assets/images/icon-close.svg" alt="menu menu-close" />
          <img v-else src="../assets/images/icon-hamburger.svg" alt="menu menu-hamburger" />
        </div>
      </div>
      <nav class="mx-auto md:block" :class="menuVisible ? 'open': 'hidden'">
        <ul class="flex flex-col md:flex-row">
          <li v-for="menuItem in menuLinks" :key="menuItem.id">
            <nuxt-link @click.native="toggleMenu" :to="menuItem.link" class="mx-2">{{menuItem.text}}</nuxt-link>
          </li>
        </ul>
      </nav>
      <div class="hidden md:block">
        <nuxt-link class="btn" to="/">Request Invite</nuxt-link>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  data() {
    return {
      menuVisible: false,
      menuLinks: [
        { text: "Home", link: "/", id: 1 },
        { text: "About", link: "/about", id: 2 },
        { text: "Contact", link: "/contact", id: 3 },
        { text: "Blog", link: "/blog", id: 4 },
        { text: "Careers", link: "/careers", id: 5 }
      ]
    };
  },
  methods: {
    toggleMenu() {
      this.menuVisible = !this.menuVisible;
    }
  }
};
</script>  
<style>
header {
  width: 100%;
  background: var(--white-clr);
  padding: 0.75rem 1rem;
  z-index: 10;
}
header .logo a {
  transform: perspective(1px) translateZ(0);
}
header .logo a:hover,
header .logo a:focus,
header .logo a:active {
  animation: logo-hover 1s ease-in-out 1;
}
header .logo a {
  display: inline-block;
}
header .logo a:focus {
  outline-style: dotted;
  outline-color: var(--accent-clr);
  outline-width: 2px;
  outline-offset: 2px;
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
.hamburger-menu img {
  width: 1rem;
  height: 1rem;
}
header .invite {
  flex-basis: auto;
}
nav li {
  position: relative;
  margin-bottom: 0.75rem;
  color: var(--grayishBlue-clr);
  font-size: 0.875rem;
}
nav li a:hover {
  color: var(--secondary-clr);
}
nav a:focus {
  color: var(--accent-clr);
}

@media screen and (min-width: 1024px) {
  nav li:hover:after {
    content: "";
    position: absolute;
    bottom: -1.55rem;
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
  header .invite {
    margin: 1rem auto;
  }
  nav.open {
    position: absolute;
    top: 3rem;
    width: 90%;
    left: 50%;
    transform: translateX(-50%);
    background: var(--white-clr);
    border-radius: 5px;
    padding: 1rem;
    box-shadow: 0px 8px 15px 15px rgba(0, 0, 0, 0.1);
  }
  nav.open li {
    font-size: 1rem;
  }
}
</style>

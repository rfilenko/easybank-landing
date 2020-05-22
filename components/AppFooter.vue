<template>
  <footer class="flex-col md:flex-row py-8">
    <div class="container justify-between flex-col md:flex-row">
      <div class="logo flex flex-col">
        <img
          class="self-center md:self-start mb-8 md:mb-12"
          src="../assets/images/logo-footer.svg"
          alt="company logo"
        />
        <FooterSocial />
      </div>
      <div class="links flex self-center mb-6">
        <ul class="flex flex-col flex-wrap md:flex-row">
          <li class="flex self-center mb-2">
            <nuxt-link to="/about">About Us</nuxt-link>
          </li>
          <li class="flex self-center mb-2">
            <nuxt-link to="/contact">Contact</nuxt-link>
          </li>
          <li class="flex self-center mb-2">
            <nuxt-link to="/blog">Blog</nuxt-link>
          </li>
          <li class="flex self-center mb-2">
            <nuxt-link to="/careers">Careers</nuxt-link>
          </li>
          <li class="flex self-center mb-2">
            <nuxt-link to="/">Support</nuxt-link>
          </li>
          <li class="flex self-center mb-2">
            <nuxt-link to="/">Privacy Policy</nuxt-link>
          </li>
        </ul>
      </div>
      <div class="rights flex flex-col md:items-end">
        <a class="btn mb-4 md:mb-8 self-center md:self-end" href="/">Request Invite</a>
        <p>&copy; Easybank. All Rights Reserved</p>
      </div>
    </div>
    <div class="attribution mt-12 md:mt-6">
      <p>
        Challenge by
        <a
          href="https://www.frontendmentor.io?ref=challenge"
          target="_blank"
          rel="noopener noreferrer"
        >Frontend Mentor</a>.
      </p>
      <p>
        Coded by
        <a class="author" href="https://rfilenko-cv.netlify.app/">@Roman Filenko</a>
      </p>
    </div>
  </footer>
</template>

<script>
import FooterSocial from "~/components/FooterSocial.vue";
export default {
  components: {
    FooterSocial
  }
};
</script>  

<style>
footer {
  margin-top: auto;
  background: var(--secondary-clr);
  color: var(--white-clr);
  font-size: 0.75rem;
}
.links {
  flex-basis: 25%;
}
.links li {
  flex-basis: calc(50% - 1rem);
}
.rights p {
  color: var(--grayishBlue-clr);
}
footer .links a:hover,
footer .links a:focus {
  color: var(--primary-clr);
  outline-color: var(--primary-clr);
}
.attribution p + p {
  margin-bottom: 0.5rem;
}
.attribution {
  @apply flex flex-col items-center;
}
.attribution .author {
  transform: perspective(1px) translateZ(0);
  background: linear-gradient(45deg, var(--primary-clr), var(--accent-clr));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  display: inline-block;
  vertical-align: middle;
  margin-left: 0.5em;
}
.attribution .author:hover,
.attribution .author:focus,
.attribution .author:active {
  transform: scale(1.05);
  transition-timing-function: cubic-bezier(0.47, 2.02, 0.31, -0.36);
  background: linear-gradient(90deg, var(--accent-clr), var(--primary-clr));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

@media screen and (max-width: 600px) {
  .links li {
    flex-basis: auto;
  }
}
</style>

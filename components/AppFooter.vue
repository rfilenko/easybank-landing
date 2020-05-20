<template>
  <footer>
    <div class="container">
      <div class="logo">
        <img src="../assets/images/logo-footer.svg" alt="company logo" />
        <div class="social-links">
          <ul>
            <li>
              <a href="/">f</a>
            </li>
            <li>
              <a href="/">t</a>
            </li>
          </ul>
        </div>
      </div>
      <div class="links">
        <ul>
          <li>
            <nuxt-link to="/about">About Us</nuxt-link>
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
          <li>
            <nuxt-link to="/">Support</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/">Privacy Policy</nuxt-link>
          </li>
        </ul>
      </div>
      <div class="rights">
        <a class="btn" href="/">Request Invite</a>
        <p>&copy; Easybank. All Rights Reserved</p>
      </div>
    </div>
    <div class="attribution">
      <p>
        Challenge by
        <a
          href="https://www.frontendmentor.io?ref=challenge"
          target="_blank"
        >Frontend Mentor</a>.
      </p>
      <p>
        Coded by
        <a href="https://rfilenko-cv.netlify.app/">@Roman Filenko</a>.
      </p>
    </div>
  </footer>
</template>
<style scoped>
footer {
  margin-top: auto;
  background: var(--secondary-clr);
  color: var(--white-clr);
  padding: 2rem 0;
  font-size: 0.75rem;
}
footer .container {
  justify-content: space-between;
}
footer .container > div {
  display: flex;
}
footer .logo {
  flex-direction: column;
}
.logo img {
  margin-bottom: 3rem;
  align-self: flex-start;
}
.links {
  flex-basis: 25%;
}
.links ul {
  display: flex;
  flex-wrap: wrap;
}
.links li {
  margin: 0 0.5rem 1rem;
  display: flex;
  flex-basis: calc(50% - 1rem);
}
.rights {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}
.rights a {
  margin-bottom: 2rem;
}
.rights p {
  color: var(--grayishBlue-clr);
}
.links a:hover {
  color: var(--primary-clr);
}
.attribution {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.attribution p + p {
  margin-bottom: 0.5rem;
}
@media screen and (max-width: 600px) {
  footer {
    flex-direction: column;
  }
  footer > div {
    flex-direction: column;
    justify-content: center;
  }
  .logo img {
    margin-bottom: 2rem;
    align-self: center;
  }
  .links ul {
    flex-direction: column;
    justify-content: center;
  }
  .links li {
    flex-basis: auto;
    align-self: center;
  }
  .rights {
    align-items: center;
  }
}
</style>

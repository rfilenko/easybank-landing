<template>
  <section class="section-articles">
    <div class="container">
      <h3>Latest articles</h3>
      <div class="wrapper">
        <div class="card" v-for="c in articles" :key="c.title">
          <img :src="getImgUrl(c.image, 'jpg')" :alt="c.title" />
          <div class="content">
            <div class="author">{{c.author}}</div>
            <div class="title">{{c.title}}</div>
            <p class="text">{{c.text}}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ["articles"],
  data() {
    return {};
  },
  methods: {
    getImgUrl(logo, format) {
      let images;
      if (format === "jpg") {
        images = require.context("../assets/images/", false, /\.jpg$/);
      } else {
        images = require.context("../assets/images/", false, /\.svg$/);
      }
      return images("./" + logo + `.${format}`);
    }
  }
};
</script>
<style>
.section-features {
  background: var(--lightGrayishBlue-clr);
}
.section-features h3 {
  margin-bottom: 1rem;
}
.section-features .subtitle {
  margin-bottom: 2.5rem;
  color: var(--grayishBlue-clr);
  max-width: 59ch;
  text-align: left;
}
.section-features .card {
  background: transparent;
}
.section-features .card img {
  width: 72px;
}
.section-features .card .text {
  color: var(--grayishBlue-clr);
}
</style>

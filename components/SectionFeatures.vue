<template>
  <section class="section-features">
    <div class="container">
      <h3>Why choose Easybank?</h3>
      <div class="subtitle">
        We leverage Open Banking to turn your bank account into your financial hub. Control
        your finances like never before.
      </div>
      <div class="wrapper">
        <div class="card" v-for="f in features" :key="f.title">
          <div class="content">
            <img :src="getImgUrl(f.icon, 'svg')" :alt="f.title" />
            <div class="title">{{f.title}}</div>
            <p class="text">{{f.feature}}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: ["features"],
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
.section-features .card {
  background: transparent;
}
.section-features .card img {
  width: 72px;
}
.section-features .card .text {
  color: var(--grayishBlue-clr);
}
@media screen and (max-width: 600px) {
  .section-features .card img {
    margin: 0 auto 1rem;
  }
  .section-features h3 {
    text-align: center;
  }
}
</style>

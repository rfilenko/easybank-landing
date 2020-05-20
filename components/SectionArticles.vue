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
</style>

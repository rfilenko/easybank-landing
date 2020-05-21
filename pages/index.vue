<template>
  <main>
    <SectionIntro />
    <SectionFeatures :features="features" />
    <SectionArticles :articles="articles" />
  </main>
</template>

<script>
import SectionIntro from "~/components/SectionIntro.vue";
import SectionFeatures from "~/components/SectionFeatures.vue";
import SectionArticles from "~/components/SectionArticles.vue";
import { articles, features } from "static/data.js";

export default {
  head: {
    title: `Easybank landing page, created with Nuxt.js`,
    meta: [
      {
        hid: "description",
        name: "description",
        content: "Easybank landing page"
      }
    ]
  },
  components: {
    SectionIntro,
    SectionFeatures,
    SectionArticles
  },
  data() {
    return {
      articles,
      features
    };
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
.container {
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

section {
  background: var(--veryLightGray-clr);
  padding: 3rem 0;
}
section h1,
section h3,
section .subtitle,
section .invite {
  align-self: flex-start;
}
section .subtitle {
  margin-bottom: 2.5rem;
  color: var(--grayishBlue-clr);
  max-width: 59ch;
  text-align: left;
}
section .container {
  flex-direction: column;
}

.wrapper {
  display: flex;
  justify-content: space-between;
}
h1,
h3 {
  margin-bottom: 2rem;
  text-align: left;
}
h1 {
  font-size: 3.75rem;
  max-width: 15ch;
  line-height: 1.2;
}
h3 {
  font-size: 2.5rem;
}
.card {
  box-shadow: 1px 1px 14px 5px hsla(180, 29%, 50%, 0.1);
  transition: all 0.15s ease;
  cursor: pointer;
  position: relative;
  max-width: clamp(25%, 400px, 18rem);
  background: #fff;
  border-radius: 5px;
}
.card:hover {
  box-shadow: 1px 1px 15px 10px hsla(180, 29%, 50%, 0.15);
}
.card .content {
  padding: 1rem 1.5rem;
  text-align: left;
}
.card .author {
  margin-bottom: 0.5rem;
  font-size: 0.75rem;
  color: var(--grayishBlue-clr);
}
.card .title {
  font-weight: bold;
  color: var(--secondary-clr);
  margin-bottom: 0.75rem;
}

.card img {
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  margin-bottom: 1rem;
  max-height: 160px;
  object-fit: cover;
  width: 100%;
  height: 100%;
}
@media screen and (min-width: 1024px) {
  .card + .card {
    margin-left: 1rem;
  }
}
@media screen and (max-width: 1024px) {
  .title {
    font-size: 24px;
    line-height: 1;
  }
}
@media screen and (max-width: 600px) {
  .wrapper {
    flex-direction: column;
    align-items: center;
  }
  .card {
    margin-bottom: 2rem;
  }
  .card .content {
    text-align: center;
  }

  section h3,
  section .subtitle {
    line-height: 1.2;
  }
  section h1,
  section h3,
  section .subtitle,
  section .invite {
    align-self: center;
  }
  section h1,
  section h3 {
    font-size: 2.25rem;
    line-height: 1;
    margin-bottom: 1rem;
  }
  section .invite {
    align-self: center;
  }
  .content {
    margin-bottom: 2rem;
  }
  section .subtitle {
    margin-bottom: 2rem;
  }
}
</style>

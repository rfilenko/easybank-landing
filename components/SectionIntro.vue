<template>
  <section class="section-intro">
    <div class="container">
      <div class="grid">
        <div class="content">
          <h1>Next generation digital banking</h1>
          <div class="subtitle">
            Take your financial life online. Your Easybank account will be a one-stop-shop
            for spending, saving, budgeting, investing, and much more.
          </div>
          <div class="invite">
            <a class="btn" href="/">Request Invite</a>
          </div>
        </div>
        <div class="abstract">
          <img src="~/assets/images/image-mockups.png" alt="mockups" />
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: [""],
  data() {
    return {};
  }
};
</script>
<style>
.section-intro {
  background-color: var(--veryLightGray-clr);
  background-image: url("/images/bg-intro-desktop.svg");
  background-position: 76vh -215px;
  background-repeat: no-repeat;
  background-size: 90%;
}
.section-intro .subtitle {
  max-width: 45ch;
}
.grid {
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 1rem;
}
.content {
  align-self: center;
  display: flex;
  flex-direction: column;
}
@media screen and (min-width: 1024px) {
  .section-intro {
    padding-top: 0;
    padding-bottom: 0;
    margin-top: -5.5rem;
    margin-bottom: -6rem;
  }
  .grid {
    grid-template-columns: 1fr 1fr;
  }
}
@media screen and (max-width: 600px) {
  .section-intro {
    background-image: url("/images/bg-intro-mobile.svg");
    background-position: top center;
    background-size: 100%;
  }
  .abstract {
    grid-row: 1;
  }
}
</style>

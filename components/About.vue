<template>
  <section class="about">
    <div class="container">
      <div class="inner-wrap">
        <h2
          v-if="content.about_title && content.about_title[0].text"
          class="section-title"
        >
          {{ content.about_title[0].text }}
        </h2>

        <div class="about-row">
          <div class="col-text">
            <h3 class="title">
              We have strong experience in
              <span>web</span>, <span>ui/ux</span>,
              <span>e-commerce</span>
            </h3>

            <p v-if="content.about_text && content.about_text[0].text">
              {{ content.about_text[0].text }}
            </p>

            <div class="btn-holder">
              <a
                v-if="content.about_btn && content.about_btn[0].text"
                href="#"
                class="btn"
              >
                {{ content.about_btn[0].text }}
              </a>
            </div>
          </div>

          <div class="col-img">
            <img
              v-if="content.about_image && content.about_image.url"
              :src="content.about_image.url"
              :alt="content.about_image.alt"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: 'About',
  components: {},
  props: {
    content: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {};
  },
};
</script>

<template>
  <section class="hero hero-about">
    <div class="container">
      <!-- <div class="hidden1">{{ content }}</div> -->

      <div class="inner-wrap">
        <div class="text-holder">
          <h1 class="title">
            {{ content.hero_title[0].text }}
            <span>{{ content.hero_title1[0].text }}</span>
            {{ content.hero_title2[0].text }}
          </h1>
          <vue-custom-scrollbar
            class="scroll-area"
            :settings="settings"
            @ps-scroll-y="scrollHanle"
          >
            <p class="hero-text">{{ content.hero_text[0].text }}</p>
          </vue-custom-scrollbar>
        </div>

        <ul class="list-holder">
          <li
            v-for="item in content.principle_holder"
            :key="item.id"
            class="principle-item"
          >
            <img
              v-if="item.list_img && item.list_img.url"
              :src="item.list_img.url"
              :alt="item.list_img.alt"
              class="ico"
            />
            <h5 class="list-title">{{ item.list_title[0].text }}</h5>
            <p class="list-text">{{ item.list_text[0].text }}</p>
          </li>
        </ul>

        <div class="img-holder">
          <img
            v-if="content.hero_bg && content.hero_bg.url"
            :src="content.hero_bg.url"
            :alt="content.hero_bg.alt"
          />
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import vueCustomScrollbar from 'vue-custom-scrollbar';
import 'vue-custom-scrollbar/dist/vueScrollbar.css';
export default {
  name: 'HeroAbout',
  components: {
    vueCustomScrollbar,
  },
  props: {
    content: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      settings: {
        suppressScrollY: false,
        suppressScrollX: false,
        wheelPropagation: false,
      },
    };
  },
  methods: {
    scrollHanle(evt) {
      console.log(evt);
    },
  },
};
</script>

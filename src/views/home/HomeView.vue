<script setup>
import SectionBegin from "./section-begin.vue";
import SectionIntro from "./section-intro.vue";
import SectionBenefit from "./section-benefit.vue";
import SectionTpl from "./section-tpl.vue";
import SectionSupport from "./section-support.vue";
import SectionFaq from "./section-faq.vue";
import SectionSocial from "./section-social.vue";
</script>

<template>
  <div class="pa-4"></div>
  <div class="pos-s top-0 z-100 bg-1">
    <div class="main">
      <header class="al-c pt-4 pb-4">
        <a href="https://www.4everland.org" target="_blank" class="mr-auto">
          <img src="/img/logo.png" height="30" />
        </a>
        <span
          class="nav-btn hover-1"
          @click="onNav(it)"
          v-for="(it, i) in headLinks"
          :key="i"
          >{{ it.text }}</span
        >
        <a
          class="bg-pink-1 btn-1 bdrs-8 hover-2"
          href="https://github.com/4everland/Templates"
          target="_blank"
          >Join Now</a
        >
      </header>
    </div>
  </div>

  <div class="main">
    <div class="pa-5"></div>
    <SectionBegin />
  </div>

  <div class="main" ref="intro">
    <div class="title-1">
      <span>Introduction</span>
    </div>
  </div>
  <auto-wrap>
    <SectionIntro />
  </auto-wrap>

  <auto-wrap ref="benefit">
    <SectionBenefit />
  </auto-wrap>

  <div class="main">
    <div class="title-1">Remarkable Templates</div>
  </div>
  <auto-wrap>
    <SectionTpl />
  </auto-wrap>

  <div class="main" ref="support">
    <div class="title-1">Community Support</div>
    <SectionSupport />
  </div>

  <SectionFaq ref="faq" />

  <div class="pa-7"></div>
  <div class="main">
    <SectionSocial />
  </div>

  <div class="pa-8"></div>
</template>

<script>
export default {
  data() {
    return {
      headLinks: [
        {
          text: "Introduction",
          ref: "intro",
        },
        {
          text: "Benefits",
          ref: "benefit",
        },
        {
          text: "Support",
          ref: "support",
        },
        {
          text: "FAQ",
          ref: "faq",
        },
      ],
    };
  },
  methods: {
    onNav(it) {
      const ref = this.$refs[it.ref];
      const el = ref.$el || ref;
      // console.log(el.offsetTop);
      window.scrollTo({
        top: el.offsetTop - 100,
        behavior: "smooth",
      });
    },
  },
};
</script>

<style lang="scss">
header {
  font-size: 18px;
  .nav-btn {
    margin-right: 45px;
  }
}
.btn-1 {
  font-weight: bold;
  padding: 10px 40px;
}
@media screen and (max-width: 800px) {
  header {
    .nav-btn {
      display: none;
    }
  }
  .btn-1 {
    padding: 8px 12px;
    font-size: 15px;
  }
}
</style>
<template>
  <div>
    <LuncherButton />
    <Header />
    <VideoMedia v-if="isDesktop" />
    <VideoMediaMobile v-if="!isDesktop" />
    <FreeProduct />
    <ShowCase />
    <WhoAreWe />
    <OurAdvantages />
    <Card3D />
    <VideoTutorials />
    <Footer />
  </div>
</template>
<script>
import Header from "./components/sections/Header.vue";
import VideoMedia from "./components/sections/VideoMedia.vue";
import VideoMediaMobile from "./components/sections/VideoMediaMobile.vue";
import VideoTutorials from "./components/sections/VideoTutorials.vue";
import Footer from "./components/sections/Footer.vue";
import FreeProduct from "./components/sections/FreeProduct.vue";
import Card3D from "./components/sections/Card3D.vue";
import ShowCase from "./components/sections/ShowCase.vue";
import OurAdvantages from "./components/sections/OurAdvantages.vue";
import WhoAreWe from "./components/sections/WhoAreWe.vue";
import LuncherButton from "./components/ui/LuncherButton.vue";
import breakpointMixin from "./mixins/breakpoint";
import htmlFontMixin from "./mixins/htmlFont";
export default {
  mixins: [breakpointMixin, htmlFontMixin],
  components: {
    Header,
    VideoMedia,
    VideoTutorials,
    Footer,
    FreeProduct,
    Card3D,
    ShowCase,
    OurAdvantages,
    WhoAreWe,
    LuncherButton,
    VideoMediaMobile,
  },
  mounted() {
    this.toggleAnimation();
  },
  methods: {
    toggleAnimation() {
      const elements = document.getElementsByClassName("aos");
      const observer = new IntersectionObserver((entries) => {
        entries.forEach((entry) => {
          const element = entry.target;
          const classAnimation = element.getAttribute("data-aos");
          if (entry.isIntersecting) {
            element.classList.add(classAnimation);
          }
        });
      });
      Array.from(elements).forEach((element) => {
        observer.observe(element);
      });
    },
  },
};
</script>
<style lang="scss"></style>

<template>
  <div class="home">
    <!-- Slick Section Start -->
    <app-home-slider :sliderData="sliderData"></app-home-slider>
    <!-- Slick Section End -->

    <app-home-feature :services="services"></app-home-feature>

    <app-home-qoute></app-home-qoute>

    <!-- WHY WORK WITH US Start -->
    <app-hopm me-why :features="features"></app-hopm>
    <!-- WHY WORK WITH US End -->
    <!-- testimonials Section Start -->
    <app-home-testimonials :testimonials="testimonials"></app-home-testimonials>
    <!-- testimonials Section End -->
    <app-home-countdown :counter="counter"></app-home-countdown>

    <app-home-technology :solutions="solutions"></app-home-technology>
    <app-home-qoute-2></app-home-qoute-2>

    <app-home-team :team="team"></app-home-team>

    <app-home-blogs :blogs="blogs"></app-home-blogs>

    <!-- <app-home-contact-divider></app-home-contact-divider> -->

    <!-- SERVICES WE PROVIDESection Start -->
    <!-- <app-home-services></app-home-services> -->
    <!-- SERVICES WE PROVIDE Section End -->

    <!-- <app-home-news></app-home-news> -->

    <!-- Services Section Start -->
    <!-- <app-home-services-offers></app-home-services-offers> -->
  </div>
</template>

<script>
// import AppHomeContactDivider from '../components/home/AppHomeContactDivider.vue'
import AppHomeFeature from "../components/home/AppHomeFeature.vue";
import AppHomeQoute from "../components/home/AppHomeQoute.vue";
// import AppHomeNews from '../components/home/AppHomeNews.vue'
// import AppHomeServices from '../components/home/AppHomeServices.vue'
// import AppHomeServicesOffers from '../components/home/AppHomeServicesOffers.vue'
import AppHomeSlider from "../components/home/AppHomeSlider.vue";
import AppHomeTestimonials from "../components/home/AppHomeTestimonials.vue";
import AppHomeWhy from "../components/home/AppHomeWhy.vue";
import AppHomeTeam from "../components/home/AppHomeTeam.vue";
import AppHomeCountdown from "../components/home/AppHomeCountdown.vue";
import AppHomeTechnology from "../components/home/AppHomeTechnology.vue";
import AppHomeBlogs from "../components/home/AppHomeBlogs.vue";
// @ is an alias to /src

export default {
  name: "Home",
  async asyncData({ $axios, app }) {
    const sliderData = await $axios.get("/sliders");

    const features = await $axios.get("/sections/features", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const solutions = await $axios.get("/sections/solutions", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const blogs = await $axios.get("/blogs?latest=1");

    const services = await $axios.get("/services");

    const testimonials = await $axios.get("/testimonials");

    const team = await $axios.get("/teams");

    const counter = await $axios.get("/sections/counter_success", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    return {
      sliderData: sliderData.data.data.sliders,
      features: features.data.data,
      solutions: solutions.data.data,
      blogs: blogs.data.data.blogs,
      services: services.data.data.services,
      testimonials: testimonials.data.data.testimonials,
      team: team.data.data.teams,
      counter: counter.data.data,
    };
  },
  components: {
    AppHomeSlider,
    AppHomeFeature,
    AppHomeQoute,
    AppHomeTeam,
    // AppHomeContactDivider,
    AppHomeWhy,
    // AppHomeServices,
    AppHomeTestimonials,
    AppHomeCountdown,
    AppHomeTechnology,
    AppHomeBlogs,
    // AppHomeNews,
    // AppHomeServicesOffers
  },
};
</script>

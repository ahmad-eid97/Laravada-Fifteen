<template>
  <div class="home">
    <!-- Slick Section Start -->
    <app-home-slider :slides="slides"></app-home-slider>

    <app-home-partners :partners="partners" />
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

    <app-home-activities :activities="activities" />
    <app-home-steps :steps="steps" />

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
import AppHomeActivities from "../components/home/AppHomeActivities.vue";
import AppHomeSteps from "../components/home/AppHomeSteps.vue";
import AppHomePartners from "../components/home/AppHomePartners.vue";
// @ is an alias to /src

export default {
  name: "Home",
  async asyncData({ $axios, app }) {
    const slides = await $axios.get("/sliders", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const partners = await $axios.get("/partners");

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

    const activities = await $axios.get("/sections/activities", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const steps = await $axios.get("/sections/steps", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    return {
      slides: slides.data.data.sliders,
      features: features.data.data,
      partners: partners.data.data.partners,
      solutions: solutions.data.data,
      blogs: blogs.data.data.blogs,
      services: services.data.data.services,
      testimonials: testimonials.data.data.testimonials,
      team: team.data.data.teams,
      counter: counter.data.data,
      activities: activities.data.data,
      steps: steps.data.data,
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
    AppHomeActivities,
    AppHomeSteps,
    AppHomePartners,
    // AppHomeNews,
    // AppHomeServicesOffers
  },
};
</script>

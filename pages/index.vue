<template>
  <div class="home">
    <!-- Slick Section Start -->
    <app-home-slider :slides="slides"></app-home-slider>

    <app-home-partners :partners="partners" />
    <!-- Slick Section End -->

    <app-home-feature :services="services"></app-home-feature>

    <app-home-qoute></app-home-qoute>

    <!-- WHY WORK WITH US Start -->
    <app-home-why :features="features"></app-home-why>
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

    <SocialChat :attendants="attendants">
      <p slot="header">Click one of our representatives below to chat.</p>
      <template v-slot:button="{ open }">
        <span v-show="!open">Contact us</span>
        <span v-show="open">Close</span>
      </template>
      <small slot="footer">Opening hours: 8am to 10pm</small>
    </SocialChat>

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
  data() {
    return {
      attendants: [
        {
          app: "whatsapp",
          label: "Support",

          name: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_whatsapp_label"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_whatsapp_label"
              ).plain_value
            : "Laravada",

          number: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_whatsapp_number"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_whatsapp_number"
              ).plain_value
            : "11111111111",

          avatar: {
            src: "https://avatars0.githubusercontent.com/u/8084606?s=460&u=20b6499a416cf7129a18e5c168cf387e159edb1a&v=4",
            alt: "Laravada customer support",
          },
        },
        {
          app: "messenger",
          label: "Technical support",

          name: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_messenger_label"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_messenger_label"
              ).plain_value
            : "Laravada Facebook",

          id: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_messenger_id"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_messenger_id"
              ).plain_value
            : "111111111111",

          avatar: {
            src: "https://avatars0.githubusercontent.com/u/8084606?s=460&u=20b6499a416cf7129a18e5c168cf387e159edb1a&v=4",
            alt: "Laravada customer support",
          },
        },
      ],
    };
  },
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

<style>
.home {
  --vsc-bg-header: var(--main-color);
  --vsc-bg-footer: var(--main-color);
  --vsc-text-color-header: #fff;
  --vsc-text-color-footer: #fff;
  --vsc-bg-button: var(--main-color);
  --vsc-text-color-button: #fff;
  --vsc-outline-color: var(--main-color);
  --vsc-border-color-bottom-header: #fff;
  --vsc-border-color-top-footer: #fff;
}
</style>

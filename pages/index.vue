<template>
  <div class="home">
        <!-- Slick Section Start -->
        <app-home-slider :sliderData="sliderData"></app-home-slider>
        <!-- Slick Section End -->
        
        <app-home-feature></app-home-feature>

        <app-home-qoute></app-home-qoute>

        <!-- WHY WORK WITH US Start -->
        <app-home-why></app-home-why>
        <!-- WHY WORK WITH US End -->
        <!-- testimonials Section Start -->
        <app-home-testimonials></app-home-testimonials>
        <!-- testimonials Section End --> 
        <app-home-countdown></app-home-countdown>

        <app-home-technology></app-home-technology>

        <app-home-team></app-home-team>

        <app-home-blogs></app-home-blogs>

        
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
import AppHomeFeature from '../components/home/AppHomeFeature.vue'
import AppHomeQoute from '../components/home/AppHomeQoute.vue'
// import AppHomeNews from '../components/home/AppHomeNews.vue'
// import AppHomeServices from '../components/home/AppHomeServices.vue'
// import AppHomeServicesOffers from '../components/home/AppHomeServicesOffers.vue'
import AppHomeSlider from '../components/home/AppHomeSlider.vue'
import AppHomeTestimonials from '../components/home/AppHomeTestimonials.vue'
import AppHomeWhy from '../components/home/AppHomeWhy.vue'
import AppHomeTeam from '../components/home/AppHomeTeam.vue'
import AppHomeCountdown from '../components/home/AppHomeCountdown.vue'
import AppHomeTechnology from '../components/home/AppHomeTechnology.vue'
import AppHomeBlogs from '../components/home/AppHomeBlogs.vue'
// @ is an alias to /src


export default {
  name: 'Home',
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
  async asyncData({ $axios }) {
    const sliderData = await $axios.get('/sliders');

    return {
      sliderData: sliderData.data.data.sliders
    }
  }
}
</script>

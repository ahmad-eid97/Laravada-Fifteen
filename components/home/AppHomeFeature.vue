<template>
  <section class="features">
    <div class="container">
      <div class="row gy-4 justify-content-center" v-if="services.length >= 1">
        <div class="col-12 text-center pt-4 pb-4">
          <h2>SERVICES WE PROVIDE</h2>
        </div>
        <div
          v-for="service in services.slice(0, 4)"
          :key="service.id"
          class="col-lg-6 col-auto"
        >
          <div class="services-card services-card-color-bg">
            <i :class="service.icon"></i>
            <h3>
              <a href="service-details.html">{{ service.title }}</a>
            </h3>
            <p>{{ service.short_description }}</p>
            <nuxt-link :to="`/service/${service.id}`" class="learn-btn"
              >Learn More <i class="bx bx-chevron-right"></i
            ></nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeFeature",
  props: ["services"],
  components: {},
  data() {
    return {};
  },
  methods: {},
};
</script>

<style>
.features {
  padding: 30px 0;
}
.services-card {
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.07);
  padding: 40px 30px 35px;
  border-radius: 15px;
  background-color: #fff;
  position: relative;
  z-index: 1;
  margin-bottom: 30px;
  height: 100%;
}
.services-card::before {
  content: "";
  position: absolute;
  z-index: -1;
  bottom: 0;
  right: 0;
  width: 90px;
  height: 90px;
  background-color: var(--main-color);
  border-radius: 272px 0 0 0;
  opacity: 0.1;
  -webkit-transition: 0.7s;
  transition: 0.7s;
}

.services-card::after {
  content: "";
  position: absolute;
  z-index: -1;
  bottom: 0;
  right: 0;
  width: 75px;
  height: 75px;
  background-color: var(--main-color);
  border-radius: 170px 0 0 0;
  opacity: 0.1;
  -webkit-transition: 0.7s;
  transition: 0.7s;
}
.services-card:hover::before {
  width: 100%;
  height: 100%;
  border-radius: 10px;
  opacity: 1;
}
.services-card i {
  color: var(--main-color);
  font-size: 60px;
  line-height: 1;
  -webkit-transition: 0.7s;
  transition: 0.7s;
}
.services-card:hover i {
  color: #fff;
}
.services-card h3 {
  margin-top: 20px;
  margin-bottom: 12px;
  -webkit-transition: 0.7s;
  transition: 0.7s;
}
.services-card h3 a {
  display: block;
  color: #252525;
  -webkit-transition: 0.7s;
  transition: 0.7s;
}
.services-card:hover h3 a {
  color: #fff;
}
.services-card p {
  margin-bottom: 12px;
  -webkit-transition: 0.7s;
  transition: 0.7s;
}
.services-card:hover p {
  color: #fff;
}
.services-card .learn-btn {
  color: #252525;
  font-size: 14px;
  font-weight: 600;
  -webkit-transition: 0.7s;
  transition: 0.7s;
}
.services-card:hover .learn-btn {
  color: #fff;
}
</style>

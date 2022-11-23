<template>
    <section class="services-style-area pt-100 pb-70">
        <div class="container">
            <div class="section-title text-center">
                <span class="sp-color2">Our Services</span>
                <h2>We Provide a Wide Variety of It Services</h2>
                <p class="margin-auto">
                Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit. Duis sed odio sit amet nibh vulputate cursus a sit amet mauris. Morbi accumsan ipsum velit. Nam nec
                </p>
            </div>
            <div class="row pt-45">
                <div v-for="service in services.services" :key="service.id" class="col-lg-3 col-sm-6 col-md-4" @click="$router.push(`/service/${service.id}`)">
                    <div class="services-card services-style-bg">
                        <div class="icon">
                            <font-awesome-icon icon="fa-solid fa-person-dots-from-line" />
                        </div>
                        <h3>
                            <router-link to="service">{{service.title}}</router-link>
                        </h3>
                        <p>{{service.description}}</p>
                        <router-link to="service" class="learn-btn">Learn More 
                            <i class="bx bx-chevron-right"></i>
                        </router-link>
                    </div>
                </div>
            </div>
            <div class="col-lg-12 col-md-12 text-center">
                <div class="pagination-area">
                    <a href="#" class=" page-numbers">
                        <font-awesome-icon icon="fa-solid fa-arrow-left" />
                    </a>
                    <span class="page-numbers current" aria-current="page">1</span>
                    <a href="#" class="page-numbers">2</a>
                    <a href="#" class="page-numbers">3</a>
                    <a href="#" class=" page-numbers">
                        <font-awesome-icon icon="fa-solid fa-arrow-right" />
                    </a>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    props: ["services"]
}
</script>

<style>
.section-title {
  margin: 0 auto;
  padding: 0;
  position: relative;
  text-align: center;
}
.section-title span {
  margin-bottom: 8px;
  font-weight: 600;
  display: block;
  color: #24b1ee;
}
.section-title p {
    margin: auto;
}
.services-style-area .section-title h2 {
  max-width: 390px;
  color: var(--main-color);
  margin-left: auto;
  margin-right: auto;
  font-size: 35px;
  font-weight: 600;
  margin-top: 0;
  line-height: 1.2;
  margin-bottom: 0;
}
.services-style-area .section-title p {
  max-width: 600px;
}
.services-card {
    box-shadow: 0 0 15px rgba(0,0,0,.07);
    padding: 40px 30px 35px;
    border-radius: 15px;
    background-color: #fff;
    position: relative;
    z-index: 1;
    margin-bottom: 30px;
    color: #24b1ee;
}
.services-card h3 a {
    color: #24b1ee;
    font-size: 26px;
}
.services-card:hover h3 a,
.services-card:hover p {
    color: #fff;
}
.services-card::before {
    content: '';
    position: absolute;
    z-index: -1;
    bottom: 0;
    right: 0;
    width: 90px;
    height: 90px;
    background-color: var(--main-color);
    border-radius: 272px 0 45px;
    opacity: .1;
    -webkit-transition: .7s;
    transition: .7s;
}

.services-card::after {

    content: '';
    position: absolute;
    z-index: -1;
    bottom: 0;
    right: 0;
    width: 75px;
    height: 75px;
    background-color: var(--main-color);
    border-radius: 170px 0  45px;
    opacity: .1;
    -webkit-transition: .7s;
    transition: .7s;
}
.services-card:hover::before {
    width: 100%;
    height: 100%;
    border-radius: 15px;
    opacity: 1;
}
.services-card .icon {
    font-size: 45px;
    width: 80px;
    height: 80px;
    line-height: 80px;
    color: #24b1ee;
    border-radius: 50px;
    display: inline-block;
    text-align: center;
    margin-bottom: 12px;
    -webkit-transition: .5s;
    transition: .5s;
}
.services-card:hover .icon {
    font-size: 45px;
    width: 80px;
    height: 80px;
    line-height: 80px;
    color: #fff;
    border-radius: 50px;
    display: inline-block;
    text-align: center;
    margin-bottom: 12px;
    -webkit-transition: .5s;
    transition: .5s;
}
</style>
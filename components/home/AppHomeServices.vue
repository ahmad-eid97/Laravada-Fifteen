<template>
  <section class="testimonials-section pb-90">
    <div class="container">
      <div class="row">
        <div class="section-title">
          <h2>SERVICES WE PROVIDE</h2>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12 testimonials-carousel-4">
          <carousel :items="4" :dots="false">
            <div class="item">
              <div class="testimonials-col">
                <div class="thumb">
                  <img src="/assets/images/testimonials/1.jpg" alt="" />
                </div>
                <div class="content">
                  <h4>Accounting and Tax Services</h4>
                  <h6>
                    Donec vestibulum lectus sem, vel convallis ligula commodo
                    ac. Aenean congue placerat risus, eu ullamcorper velit
                    maximus sed.
                  </h6>
                </div>
              </div>
            </div>
            <div class="item">
              <div class="testimonials-col">
                <div class="thumb">
                  <img src="/assets/images/testimonials/3.jpg" alt="" />
                </div>
                <div class="content">
                  <h4>Business Consulting</h4>
                  <h6>
                    Donec vestibulum lectus sem, vel convallis ligula commodo
                    ac. Aenean congue placerat risus, eu ullamcorper velit
                    maximus sed.
                  </h6>
                </div>
              </div>
            </div>
            <div class="item">
              <div class="testimonials-col">
                <div class="thumb">
                  <img src="/assets/images/testimonials/2.jpg" alt="" />
                </div>
                <div class="content">
                  <h4>Investment and Stock Exchange</h4>
                  <h6>
                    Donec vestibulum lectus sem, vel convallis ligula commodo
                    ac. Aenean congue placerat risus, eu ullamcorper velit
                    maximus sed.
                  </h6>
                </div>
              </div>
            </div>
            <div class="item">
              <div class="testimonials-col">
                <div class="thumb">
                  <img src="/assets/images/testimonials/4.jpg" alt="" />
                </div>
                <div class="content">
                  <h4>Business Advisory</h4>
                  <h6>
                    Donec vestibulum lectus sem, vel convallis ligula commodo
                    ac. Aenean congue placerat risus, eu ullamcorper velit
                    maximus sed.
                  </h6>
                </div>
              </div>
            </div>
            <div class="item">
              <div class="testimonials-col">
                <div class="thumb">
                  <img src="/assets/images/testimonials/5.jpg" alt="" />
                </div>
                <div class="content">
                  <h4>International Banking</h4>
                  <h6>
                    Donec vestibulum lectus sem, vel convallis ligula commodo
                    ac. Aenean congue placerat risus, eu ullamcorper velit
                    maximus sed.
                  </h6>
                </div>
              </div>
            </div>
            <div class="item">
              <div class="testimonials-col">
                <div class="thumb">
                  <img src="/assets/images/testimonials/6.jpg" alt="" />
                </div>
                <div class="content">
                  <h4>Finance and Banking</h4>
                  <h6>
                    Donec vestibulum lectus sem, vel convallis ligula commodo
                    ac. Aenean congue placerat risus, eu ullamcorper velit
                    maximus sed.
                  </h6>
                </div>
              </div>
            </div>
          </carousel>
          <i class="fa-solid fa-angle-right next"></i>
          <i class="fa-solid fa-angle-left prev"></i>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import carousel from "vue-owl-carousel";

export default {
  name: "AppHomeServices",
  components: { carousel },
  data() {
    return {};
  },
  methods: {},
};
</script>
<style>
.testimonials-carousel-4 {
  position: relative;
}
.testimonials-carousel-4 .owl-carousel {
  background: #fff;
}
.testimonials-carousel-4 .owl-carousel .owl-item {
  padding: 35px 15px;
}
.testimonials-carousel-4 .owl-theme .owl-nav .owl-next,
.testimonials-carousel-4 .owl-theme .owl-nav .owl-next:hover,
.testimonials-carousel-4 .owl-theme .owl-nav .owl-prev,
.testimonials-carousel-4 .owl-theme .owl-nav .owl-prev:hover {
  background: var(--gradient-background);
  color: transparent;
  display: inline-block;
  height: 75px;
  width: 24px;
  top: 197px;
  text-align: center;
  line-height: 75px;
  font-size: 18px;
  position: absolute;
}
.testimonials-carousel-4 .owl-nav .owl-next {
  right: 0px;
}
.testimonials-carousel-4 .owl-nav .owl-prev {
  left: 0px;
}
.next {
  display: inline-block;
  top: 232px;
  text-align: center;
  line-height: 75px;
  font-size: 18px;
  position: absolute;
  color: #fff;
  right: 24px;
  z-index: 2;
}
.prev {
  display: inline-block;
  top: 232px;
  text-align: center;
  line-height: 75px;
  font-size: 18px;
  position: absolute;
  color: #fff;
  left: 24px;
  z-index: 2;
}
</style>

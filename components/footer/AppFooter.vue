<template>
  <section class="footer">
    <subscribe />
    <div class="d-flex justify-content-around pt-5 responsive-footer">
      <div class="w-30 mt-2 w-control">
        <img
          src="/assets/images/logo.png"
          alt="logoImage"
          style="width: 250px"
        />
        <p class="text-light my-2 fs-5">
          Nam id sem quis mauris porttitor conse quat id vitae dolor – mauris
          lorem ipsum nulla it amet ultricies mi dolor at pharetra.
        </p>
        <button class="btn test-btn mt-3">Get in touch!</button>
      </div>

      <div class="text-light w-30 mt-2 w-control">
        <h5 class="fw-bold mb-4">Contact info</h5>
        <p class="my-3 footer-text">
          Cum sociis natoque penatibus et magnis dis parturient montes, nascetur
          ridiculus mus.
        </p>

        <p class="">Phone number</p>
        <p class="footer-text">+001 234 56 78</p>

        <p class="">Email</p>
        <p class="footer-text">
          {{
            $store.state.websiteSettings.find((one) => one.key === "email")
              .plain_value
          }}
        </p>

        <p class="">Address</p>
        <p class="footer-text">Highland St. Tonawanda, NY 14150</p>

        <div class="d-flex d-none d-lg-flex d-md-none">
          <div class="footer-icon fs-12">
            <i class="fa-brands fa-facebook-f"></i>
          </div>
          <div class="footer-icon fs-12">
            <i class="fa-brands fa-twitter"></i>
          </div>
          <div class="footer-icon fs-12">
            <i class="fa-brands fa-google"></i>
          </div>
        </div>
      </div>

      <div class="w-30 mt-2 w-control">
        <h5 class="text-light fw-bold mb-4">Recent posts</h5>

        <div>
          <div class="d-flex">
            <img
              class="footer-article-img"
              src="/assets/images/im001.jpg"
              alt=""
            />
            <div class="ms-2">
              <p class="text-light my-0">
                Glavrida sit amet – post with side images
              </p>
              <p class="footer-text my-0">16th November 2018</p>
            </div>
          </div>
          <div class="d-flex mt-4">
            <img
              class="footer-article-img"
              src="/assets/images/im001.jpg"
              alt=""
            />
            <div class="ms-2">
              <p class="text-light my-0">
                Glavrida sit amet – post with side images
              </p>
              <p class="footer-text my-0">16th November 2018</p>
            </div>
          </div>
          <div class="d-flex mt-4">
            <img
              class="footer-article-img"
              src="/assets/images/im001.jpg"
              alt=""
            />
            <div class="ms-2">
              <p class="text-light my-0">
                Glavrida sit amet – post with side images
              </p>
              <p class="footer-text my-0">16th November 2018</p>
            </div>
          </div>
          <div class="d-flex mt-4">
            <img
              class="footer-article-img"
              src="/assets/images/im001.jpg"
              alt=""
            />
            <div class="ms-2">
              <p class="text-light my-0">
                Glavrida sit amet – post with side images
              </p>
              <p class="footer-text my-0">16th November 2018</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="footer-border footer-text">
      <img src="/assets/images/l-b-s.webp" alt="" />
      <p>© Powered By: Rail Coder - 2018-2019. All rights reserved.</p>
    </div>
  </section>
</template>

<script>
import Subscribe from '../subscribe/subscribe.vue';
export default {
  name: "AppFooter",
  components: {Subscribe},
  data() {
    return {};
  },
  beforeMount() {},
  methods: {},
};
</script>

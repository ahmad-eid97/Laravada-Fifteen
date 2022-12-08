<template>
  <section class="blog-area pt-100 pb-70">
    <div class="container">
      <div class="section-title text-center">
        <span class="sp-color2">Latest Blog</span>
        <h2>Let’s Check Some Latest Blog</h2>
      </div>

      <div class="row pt-45 justify-content-center" v-if="blogs.length >= 1">
        <div
          v-for="blog in blogs.slice(0, 3)"
          :key="blog.id"
          class="col-lg-4 col-md-6"
        >
          <div class="blog-item">
            <div class="blog-img2">
              <a href="#">
                <img :src="blog.image" alt="Blog Images" />
              </a>
              <div class="blog-tag">
                <h3>{{ $date(new Date(blog.publish_date), "dd") }}</h3>
                <span>{{ $date(new Date(blog.publish_date), "MMM") }}</span>
              </div>
            </div>
            <div class="content">
              <h3>
                <a href="#">{{ blog.title }}</a>
              </h3>
              <p>{{ blog.short_description }}</p>
              <nuxt-link :to="`/blog/${blog.id}`" class="read-btn"
                >Read More <i class="fa-solid fa-angle-right"></i
              ></nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeContactDivider",
  props: ["blogs"],
  components: {},
  data() {
    return {};
  },
  methods: {},
};
</script>

<style>
.blog-item {
  background-color: #fff;
  -webkit-box-shadow: 0 0 15px rgba(0, 0, 0, 0.05);
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.05);
  margin-bottom: 30px;
  border-radius: 5px;
  -webkit-transition: 0.9s;
  transition: 0.9s;
}
.blog-item .blog-img2 {
  position: relative;
}
.blog-item .blog-img2 img {
  border-radius: 5px;
  padding: 20px;
  background-color: #e6f1fc;
  width: 100%;
  height: 300px;
}
.blog-item .blog-img2 .blog-tag {
  background-color: #0071dc;
  padding: 10px 14px 8px;
  position: absolute;
  top: 30px;
  right: 30px;
  text-align: center;
}
.blog-item .blog-img2 .blog-tag h3 {
  font-size: 20px;
  color: #fff;
  line-height: 1;
  margin-bottom: 2px;
  font-weight: 600;
}
.blog-item .blog-img2 .blog-tag span {
  color: #fff;
  line-height: 1;
  font-weight: 400;
  font-size: 15px;
}
.blog-item .content {
  padding: 25px 21px;
}
.blog-item .content h3 {
  margin-bottom: 10px;
  font-size: 22px;
}
.blog-item .content h3 a {
  color: #252525;
  text-decoration: none;
}
.blog-item .content .read-btn {
  color: #0071dc;
  font-size: 14px;
  font-weight: 600;
  text-decoration: none;
}
.blog-item:hover {
  -webkit-transform: translateY(-10px);
  transform: translateY(-10px);
}
</style>

<template>
    <section class="testimonial-section pb-70">
        <div class="container">
            <h2 class="text-center">Our Clients Feedback</h2>
            <div class="row testimonials-post">
                <div class="col-md-12">
                    <swiper :options="swiperOption" class="owl-carousel">
                        <swiper-slide v-for="item in testimonials" :key="item.id">
                            <div class="item">
                                <div class="row align-items-center">
                                    <div class="col-lg-6">
                                        <div class="clients-slider-img">
                                            <img :src="item.image" :alt="item.title">
                                            <div class="clients-slider-circle"></div>
                                        </div>
                                    </div>
                                    <div class="col-lg-6">
                                        <div class="clients-slider-content">
                                            <div class="svg">
                                                <font-awesome-icon icon="fa-solid fa-quote-left" />
                                            </div>
                                            <p>
                                                {{item.description}}
                                            </p>
                                            <h3>{{item.title}}</h3>
                                            <span>{{item.job}}</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </swiper-slide>
                    </swiper>
                    <font-awesome-icon class="next" icon="fa-solid fa-angle-right" />
                    <font-awesome-icon class="prev" icon="fa-solid fa-angle-left" />
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppHomeTestimonials',
    props: ["testimonials"],
    data() {
        return {
        swiperOption: {
            loop: true,
            slidesPerView: 1,
            spaceBetween: 50,
        },
        }
    },
    methods : {
        
    }
}
</script>
<style>
    .clients-slider-content {
        margin-top: 40px;
        text-align: center;
    }
    .testimonials-post .owl-carousel {
        background-color: transparent;
    }
    .testimonials-post .owl-nav {
        margin: 0;
    }
    .testimonials-post .owl-theme .owl-nav .owl-next,
    .testimonials-post .owl-theme .owl-nav .owl-next:hover, 
    .testimonials-post .owl-theme .owl-nav .owl-prev, 
    .testimonials-post .owl-theme .owl-nav .owl-prev:hover {
        background-color: transparent;
        display: inline-block;
        border-radius: 30px;
        bottom: 50px;
        text-align: center;
        line-height: 26px;
        font-size: 20px;
        position: absolute;
        padding: 4px 11px;
        border: 1px solid var(--main-color);
        color: var(--main-color);
    }
    .testimonials-post .owl-theme .owl-nav .owl-next:hover, 
    .testimonials-post .owl-theme .owl-nav .owl-prev:hover {
        background: var(--main-color);
        color: #fff;
        transition: all 0.2s linear;
    }
    .testimonials-post .owl-theme .owl-nav .owl-next {
        right: 30px !important;
    }
    .testimonials-post .owl-theme .owl-nav .owl-prev {
        right: 90px !important;
    }
</style>
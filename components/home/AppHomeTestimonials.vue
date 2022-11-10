<template>
    <section class="testimonial-section">
        <div class="container">
            <h2 class="text-center">Our Clients Feedback</h2>
            <div class="row testimonials-post">
                <div class="col-md-12">
                    <swiper :options="swiperOption" class="owl-carousel">

                        <swiper-slide>
                            <div class="item">
                                <div class="row align-items-center">
                                    <div class="col-lg-6">
                                        <div class="clients-slider-img">
                                            <img src="/assets/images/client-1.png" alt="Images">
                                            <div class="clients-slider-circle"></div>
                                        </div>
                                    </div>
                                    <div class="col-lg-6">
                                        <div class="clients-slider-content">
                                            <div class="svg">
                                                <font-awesome-icon icon="fa-solid fa-quote-left" />
                                            </div>
                                            <p>
                                                “Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse at ligula eget lectus consequat volutpat. Donec elit libero, finibus eget scelerisque sed, tempor sit amet erat. Pellentesque tincidunt a purus sit amet ullamcorper. Vestibulum ultrices ligula in pharetra sagittis. Quisque lacinia magna dolor, at tempus sem consequat at.”
                                            </p>
                                            <h3>Jonthon Martin</h3>
                                            <span>App Developer</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </swiper-slide>

                        <swiper-slide>
                            <div class="item">
                                <div class="row align-items-center">
                                    <div class="col-lg-6">
                                        <div class="clients-slider-img">
                                            <img src="/assets/images/client-1.png" alt="Images">
                                            <div class="clients-slider-circle"></div>
                                        </div>
                                    </div>
                                    <div class="col-lg-6">
                                        <div class="clients-slider-content">
                                            <div class="svg">
                                                <font-awesome-icon icon="fa-solid fa-quote-left" />
                                            </div>
                                            <p>
                                                “Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse at ligula eget lectus consequat volutpat. Donec elit libero, finibus eget scelerisque sed, tempor sit amet erat. Pellentesque tincidunt a purus sit amet ullamcorper. Vestibulum ultrices ligula in pharetra sagittis. Quisque lacinia magna dolor, at tempus sem consequat at.”
                                            </p>
                                            <h3>Jonthon Martin</h3>
                                            <span>App Developer</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </swiper-slide>

                        <!-- <div class="swiper-button-next" slot="button-next"></div>
                        <div class="swiper-button-prev" slot="button-prev"></div> -->

                    </swiper>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppHomeTestimonials',
    data() {
        return {
            swiperOption: {
                loop: true,
                slidesPerView: 1,
                spaceBetween: 50,
                navigation: { nextEl: '.swiper-button-prev', prevEl: '.swiper-button-next', },
            },
        }
    },
    methods : {
        
    }
}
</script>
<style>
    
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
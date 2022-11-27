<template>
    <section class="slider-wrapper home-slider p-0">

        <div class="row">

            <div class="col-lg-5 col-sm-12">
                    <div class="text">
                        <img class="overlay" src="/assets/images/slider-over.png" alt="">
                        <h1>Laravada</h1>
                        <p>The7 Welcomes Laravada</p>
                    </div>
            </div>

            <div class="col-lg-7 col-sm-12">

            <!-- Wrapper For Slides -->
                    <VueSlickCarousel :fade="true" ref="c1" :asNavFor="$refs.c2" :arrows="false" :slidesToShow="1" :focusOnSelect="true" :dots="false" class="main" >
                        <div class="item" :style="image1">
                            <img src="/assets/images/slide-1.jpg" class="img-fluid">  
                        </div>
                        <div class="item" :style="image2">
                            <img src="/assets/images/slide-2.jpg" class="img-fluid"> 
                        </div>
                        <div class="item" :style="image3">
                            <img src="/assets/images/slide-3.jpg" class="img-fluid"> 
                        </div>
                    </VueSlickCarousel>
                <!-- Indicators -->
                    <VueSlickCarousel
                        ref="c2"
                        v-show="c1"
                        :asNavFor="$refs.c1"
                        :slidesToShow="5"
                        :focusOnSelect="true" :dots="false" :arrows="false" class="thumb">
                            <img src="/assets/images/slide-1.jpg" class="img-fluid">  
                            <img src="/assets/images/slide-2.jpg" class="img-fluid"> 
                            <img src="/assets/images/slide-3.jpg" class="img-fluid"> 
                    </VueSlickCarousel>

            </div>

        </div>
                 
        </section>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
 import 'vue-slick-carousel/dist/vue-slick-carousel.css'; 
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

export default {
    name: 'AppHomeSlider',
    components: {VueSlickCarousel},
    props: ["sliderData"],
    data() {
        return {
            c1: undefined,
            c2: undefined,
            image1: {backgroundImage: "url(/img/slide-1.2cbb442e.jpg)"},
            image2: {backgroundImage: "url(/img/slide-2.2be9a187.jpg)"},
            image3: {backgroundImage: "url(/img/slide-3.74362df8.jpg)"}
        }
    },
    methods : {
        
    },
    mounted() {
        this.c1 = this.$refs.c1;
        this.c2 = this.$refs.c2;
    },
}
</script>
<style lang="scss">

    .slider-wrapper {
        position: relative;
        background: var(--main-color);
    }
    .slider-wrapper .text {
        position: absolute;
        z-index: 4;
        color: #fff;
        top: 0;
        height: 100%;
        width: 60%;
        @include sm {
            h1 {
                font-size: 50px;
            }
            p {
                font-size: 30px;
            }
            .overlay {
                display: none;
            }
        }
    }
    .slider-wrapper .text::after {
        position: absolute;
        background-color: #075aa499;
        width: 100%;
        content: '';
        height: 70%;
        top: 0;
        left: 20px;
        transform: skew(20deg);
        z-index: -1;
    }
    .slider-wrapper h1 {
        font-size: 150px;
        position: relative;
        z-index: 2;
        margin: 100px 110px 0;
    }
    .slider-wrapper p {
        font-size: 50px;
        position: relative;
        z-index: 2;
        margin: 0 0 0 110px;
    }
    .slider-wrapper .overlay {
        position: absolute;
        top: 0;
        z-index: 1;
        height: 100%;
        
    }
    .main .item {
        position: relative;
    }
    .main .item {
        min-height: 80vh;
        width: 100%;
        background-repeat: no-repeat;
        background-size: cover;
    }
    
    .home-slider .thumb  {
        width: 400px;
        position: absolute !important;
        bottom: 0;
        right: 0;
        z-index: 3;
        background: rgb(21, 26, 99);
        padding: 5px;
    }
    .home-slider .thumb .slick-slide {
        padding: 5px;
        cursor: pointer;
    }
    .home-slider .thumb img {
        border: 2px solid transparent;
    }
    .home-slider .thumb img:hover {
        border: 2px solid #fff;
    }
    .home-slider .thumb .slick-current img {
        border: 2px solid #fff;
    }
</style>
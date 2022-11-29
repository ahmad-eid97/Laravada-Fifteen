<template>
   <section class="team-section bg-f8 text-center">
        <div class="container">
            <div class="row">
                <div class="section-title">

                    <h2 class="mb-5">OUR TEAM</h2>

                </div>
            </div>
            <div class="row">
                <div class="col-12 slider-container">
                    <swiper :options="swiperOption" class="owl-carousel">
                        <swiper :options="swiperOption" class="team">
                            <swiper-slide v-for="member in team" :key="member.id">
                            <div class="item">
                                <div class=" projects-col">

                                    <div class="">
                                        <img :src="member.image" :alt="member.title">
                                    </div>
                                    <div class="content">
                                        <h4>{{member.name}}</h4>
                                        <h5>{{member.job}}</h5>
                                        <h6>{{member.description}}</h6>

                                    </div>
                                </div>
                            </div>
                            </swiper-slide>
                        </swiper>
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
    name: 'AppHomeTeam',
    props: ["team"],
    data() {
        return {
            swiperOption: {
                loop: true,
                slidesPerView: 5,
                spaceBetween: 50,
                breakpoints: {
                // when window width is >= 320px
                100: {
                    slidesPerView: 1,
                    spaceBetween: 5,
                },
                // when window width is >= 480px
                480: {
                    slidesPerView: 1,
                    spaceBetween: 5,
                },
                // when window width is >= 640px
                640: {
                    slidesPerView: 2,
                    spaceBetween: 5,
                },
                992: {
                    slidesPerView: 3,
                    spaceBetween: 5,
                },
                1200: {
                    slidesPerView: 3,
                    spaceBetween: 5,
                },
                },
            },
        }
    },
    methods : {
        
    }
}
</script>

<style scoped lang="scss">
.team-section {
    padding: 30px;
}
.slider-container {
    position: relative;
}
.slider-container .team {
    background: #fff;
}
.slider-container .team .owl-item {
    padding: 50px 50px;
}

.overview-icon {
    height: 34px !important;
}
.overview-icon .one {
    position: static !important;
    font-size: 23px !important;
    text-align: center;
}
@keyframes border-transform {
    0%, 100% {
        border-radius: 50% 50% 50% 50% / 50% 50% 50% 50%;
    }
    14% {
        border-radius: 50% 20% 50% 30% / 49% 60% 40% 51%;
    }
    28% {
        border-radius: 54% 46% 38% 62% / 49% 70% 30% 51%;
    }
    42% {
        border-radius: 61% 39% 55% 45% / 61% 38% 62% 39%;
    }
    56% {
        border-radius: 61% 39% 67% 33% / 70% 50% 50% 30%;
    }
    70% {
        border-radius: 50% 50% 34% 66% / 56% 68% 32% 44%;
    }
    84% {
        border-radius: 46% 54% 50% 50% / 35% 61% 39% 65%;
    }
}

.team img {
    border-radius: 50%;
    width: 70%;
    height: 200px;
    margin-bottom: 30px;
    animation: border-transform 15s infinite ease-in-out !important;
}
img {
    animation: border-transform 15s infinite ease-in-out !important;
    margin-bottom: 10px;
}
.team .content h4 {
  color: #1f365c;
  font-size: 20px;
  margin-bottom: 10px;
  letter-spacing: 1px;
  text-transform: uppercase;
}
.team .content h5 {
  color: #1f365c;
  font-size: 16px;
  margin-bottom: 20px;
  letter-spacing: 1px;
  text-transform: uppercase;
}
.team .content h6 {
  color: #989898;
  font-family: 'Open Sans', sans-serif;
  font-size: 14px;
  text-transform: uppercase;
  margin-bottom: 15px;
  line-height: 28px;
  letter-spacing: 0.3px;
}
.team .content h5 {
  color: #1f365c;
  font-size: 16px;
  margin-bottom: 20px;
  letter-spacing: 1px;
  text-transform: uppercase;
}
.team .content h3 {
  color: var(--main-color);
  font-size: 16px;
  margin-bottom: 20px;
  letter-spacing: 1px;
  text-transform: uppercase;
}

.team .owl-theme .owl-nav .owl-next,
    .team .owl-theme .owl-nav .owl-next:hover, 
    .team .owl-theme .owl-nav .owl-prev, 
    .team .owl-theme .owl-nav .owl-prev:hover {
        background-color: transparent;
        display: inline-block;
        border-radius: 30px;
        bottom: 0;
        text-align: center;
        line-height: 26px;
        font-size: 20px;
        position: absolute;
        padding: 4px 11px;
        border: 1px solid var(--main-color);
        color: var(--main-color);
    }
    .team .owl-theme .owl-nav .owl-next:hover, 
    .team .owl-theme .owl-nav .owl-prev:hover {
        background: var(--main-color);
        color: #fff;
        transition: all 0.2s linear;
    }
    .team .owl-theme .owl-nav .owl-next {
        right: 45% !important;
    }
    .team .owl-theme .owl-nav .owl-prev {
        right: 50% !important;
    }
</style>
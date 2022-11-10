<template>
    <section class="about-intro">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-lg-6">
                    <div class="clients-slider-img">
                        <img src="/assets/images/about-img5.png" alt="About Images">
                        <div class="clients-slider-circle"></div>
                    </div>
                </div>
                <div class="col-lg-6">
                    <div class="">
                        <h5 class="mt-5">About Your Company</h5>
                        <h2>
                            We Are Increasing Business With Promising It Services
                        </h2>
                        <p>
                            Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit. Duis sed odio sit amet nibh vulputate cursus a sit amet mauris. Morbi accumsan ipsum auctor a ornare odio. 
                        </p>
                        <h3>We Have 22+ Years Of Experience. We Offer It Solutions , Digital Technology Service</h3>
                        <div class="skill-bar" data-percentage="90%">
                            <h4 class="progress-title-holder clearfix">
                                <span class="progress-title">Analytics</span>
                            </h4>
                            <div class="progress">
                                <div class="progress-bar" role="progressbar" style="width: 90%" aria-valuenow="90" aria-valuemin="0" aria-valuemax="100"></div>
                            </div>
                            <h4 class="progress-title-holder clearfix">
                                <span class="progress-title">Solutions</span>
                            </h4>
                            <div class="progress">
                                <div class="progress-bar" role="progressbar" style="width: 80%" aria-valuenow="80" aria-valuemin="0" aria-valuemax="100"></div>
                            </div>
                                
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppAboutIntro'

}
</script>

<style>
    .about-intro {
        background-color: #f8f8f8;
    }
    .about-intro .clients-slider-img {
        position: relative;
    }
    .about-intro .clients-slider-img img {
        position: relative;
        z-index: 1;
    }
    .about-intro .clients-slider-img .clients-slider-circle {
        position: absolute;
        z-index: 0;
        bottom: -10px;
        left: -35px;
        right: 0;
        margin: 0 auto;
        text-align: center;
        width: 100%;
        height: 80%;
        -webkit-animation: border-transform 15s infinite ease-in-out;
        animation: border-transform 15s infinite ease-in-out;
        background: rgb(255,182,27);
        background: linear-gradient(180deg, #24b1ee 0%, var(--main-color) 100%); 
    }
    .about-intro h5 {
        margin-bottom: 8px;
        font-weight: 600;
        display: block;
        color: #24b1ee;
    }
    .about-intro h2 {
        font-size: 35px;
        font-weight: 600;
        margin-top: 0;
        line-height: 1.2;
        color: var(--main-color);
        margin-bottom: 0;
    }
    .about-intro p {
        color: #9c9c9c;
        padding-top: 10px;
        margin-bottom: 0;
        max-width: 530px;
        margin-bottom: 20px;
    }
    .about-intro h3 {
        font-size: 20px;
        margin-bottom: 20px;
        font-weight: 600;
        color: var(--main-color);
    }
    .about-intro h4 {
        font-size: 16px;
        font-weight: 600;
        color: var(--main-color);
        margin-bottom: 15px;
    }
    .about-intro .progress {
        height: 10px;
        background-color: rgba(255, 181, 54, 0.18);
        border-radius: 5px;
        margin-bottom: 20px;
    }
    .about-intro .progress-bar {
        background-color: #24b1ee;
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
</style>
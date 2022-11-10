<template>
    <section class="features">
        <div class="container">
            <div class="row gy-4 justify-content-center">
                <div class="col-12 text-center">
                    <h2>SERVICES WE PROVIDE</h2>
                </div>
                <div class="col-lg-6 col-auto">
                    <div class="services-card  services-card-color-bg">
                        <font-awesome-icon icon="fa-solid fa-person-dots-from-line" />
                        <h3>
                            <a href="service-details.html">IT Consulting</a>
                        </h3>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse at ligula eget lectus consequat volutpat.</p>
                        <a href="service-details.html" class="learn-btn">Learn More <i class="bx bx-chevron-right"></i></a>
                        </div>
                </div>
                <div class="col-lg-6 col-auto">
                    <div class="services-card  services-card-color-bg">
                        <font-awesome-icon icon="fa-solid fa-cloud" />
                        <h3>
                            <a href="service-details.html">Cloud Computing</a>
                        </h3>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse at ligula eget lectus consequat volutpat.</p>
                        <a href="service-details.html" class="learn-btn">Learn More <i class="bx bx-chevron-right"></i></a>
                        </div>
                </div>
                <div class="col-lg-6 col-auto">
                    <div class="services-card  services-card-color-bg">
                        <font-awesome-icon icon="fa-solid fa-laptop-code" />
                        <h3>
                            <a href="service-details.html">Web Development</a>
                        </h3>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse at ligula eget lectus consequat volutpat.</p>
                        <a href="service-details.html" class="learn-btn">Learn More <i class="bx bx-chevron-right"></i></a>
                        </div>
                </div>
                <div class="col-lg-6 col-auto">
                    <div class="services-card  services-card-color-bg">
                        <font-awesome-icon icon="fa-solid fa-chart-area" />
                        <h3>
                            <a href="service-details.html">Business Reform</a>
                        </h3>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse at ligula eget lectus consequat volutpat.</p>
                        <a href="service-details.html" class="learn-btn">Learn More <i class="bx bx-chevron-right"></i></a>
                        </div>
                </div>
            </div>

        </div>
    </section>
</template>

<script>


export default {
    name: 'AppHomeFeature',
    components: {},
    data() {
        return {
            
        }
    },
    methods : {
        
    }
}
</script>

<style>
    .features {
        padding: 30px 0;
    }

    .services-card {
        box-shadow: 0 0 15px rgba(0,0,0,.07);
        padding: 40px 30px 35px;
        border-radius: 15px;
        background-color: #fff;
        position: relative;
        z-index: 1;
        margin-bottom: 30px;
    }
    .services-card::before {
        content: '';
        position: absolute;
        z-index: -1;
        bottom: 0;
        right: 0;
        width: 90px;
        height: 90px;
        background-color: #24b1ee;
        border-radius: 272px 0 0 0;
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
        background-color: #24b1ee;
        border-radius: 170px 0 0 0;
        opacity: .1;
        -webkit-transition: .7s;
        transition: .7s;

    }
    .services-card:hover::before {
        width: 100%;
        height: 100%;
        border-radius: 10px;
        opacity: 1;
    }
    .services-card svg {
        color: #24b1ee;
        font-size: 60px;
        line-height: 1;
        -webkit-transition: .7s;
        transition: .7s;
    }
    .services-card:hover svg {
        color: #fff;
    }
    .services-card h3 {
        margin-top: 20px;
        margin-bottom: 12px;
        -webkit-transition: .7s;
        transition: .7s;
    }
    .services-card h3 a {
        display: block;
        color: #252525;
        -webkit-transition: .7s;
        transition: .7s;
    }
    .services-card:hover h3 a {
        color: #fff;
    }
    .services-card p {
        margin-bottom: 12px;
        -webkit-transition: .7s;
        transition: .7s;
    }
    .services-card:hover p {
        color: #fff;
    }
    .services-card .learn-btn {
        color: #252525;
        font-size: 14px;
        font-weight: 600;
        -webkit-transition: .7s;
        transition: .7s;
    }
    .services-card:hover .learn-btn {
        color: #fff;
    }
    .features svg {
        max-width: 80px;
    }
</style>
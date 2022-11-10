<template>
    <section class="service-section bg-f9">
        <div class="container">
            <div class="row">
                <div class="col-md-6 col-lg-3">
                    <div class="service-item style-2 img-1">
                        <div class="content">
                            <h5>20% OFF FOR ALL ACCOUNTING SERVICES</h5>
                            <a href="#">Click to view details <font-awesome-icon icon="fa-solid fa-angle-right" /></a>

                        </div>
                    </div>
                </div>
                <div class="col-md-6 col-lg-3">
                    <div class="service-item style-2 img-1">
                        <div class="content">
                            <h5>20% OFF FOR ALL ACCOUNTING SERVICES</h5>
                            <a href="#">Click to view details <font-awesome-icon icon="fa-solid fa-angle-right" /></a>

                        </div>
                    </div>
                </div>
                <div class="col-md-6 col-lg-3">
                    <div class="service-item style-2 img-1">
                        <div class="content">
                            <h5>20% OFF FOR ALL ACCOUNTING SERVICES</h5>
                            <a href="#">Click to view details <font-awesome-icon icon="fa-solid fa-angle-right" /></a>

                        </div>
                    </div>
                </div>
                <div class="col-md-6 col-lg-3">
                    <div class="service-item style-2 img-2">
                        <div class="content">
                            <h5>20% OFF FOR ALL ACCOUNTING SERVICES</h5>
                            <a href="#">Click to view details <font-awesome-icon icon="fa-solid fa-angle-right" /></a>

                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>

<script>

export default {
    name: 'AppHomeServicesOffers',
    components: {},
    data() {
        return {
            show: 'show1'
        }
    },
    mounted() {
        this.autoPlay();
    },
    methods: {
        autoPlay() {
            var items = ['show1', 'show2', 'show3', 'show4', 'show5'];
            var item = ''
            let _this = this
            setInterval(function() { 
                
                item = items[Math.floor(Math.random()*items.length)];
                _this.showData(item);
            }, 5000);
        },
        showData(show) {
            this.show = show
        }
    }
}
</script>

<style>
    .service-item a {
        color: #fff;
        font-size: 16px;
        font-weight: bold;
        padding: 15px 20px;
        transform: translateX(300%);
        position: absolute;
    }
    .service-item:hover a {
        transform: translateX(0);
    }
    
</style>
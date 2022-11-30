<template>
   <section class="about-sec">
        <div class="container">
            <div class="row">
                <div class="section-title">
                    <h2>WHY WORK WITH US</h2>
                </div>
            </div>
            <div class="row gy-4 justify-content-center align-items-center">

                <div class="col-md-6 ">
                    <div class="aboutus right">
                        <h3>
                            5 MAIN REASONS TO CHOOSE US
                        </h3>
                        <div v-for="(feature, index) in features.find(one => one.key === 'features_text_list').value" :key="index" class="about-item mb-20">
                            <div class="about-details">
                                <p>{{feature.description}}</p>

                            </div>
                            <div class="about-icon">
                                <font-awesome-icon :icon="`fa-solid fa-${index+1}`" />
                            </div>
                        </div>
                    </div>
                </div>

                <div class="col-md-6 ">
                    <div class="about-us">
                        <div class="about-us-list">
                            <div class="about-us-icon-a about-us-icon" :class="show == 'show1' ? 'active' : ''">
                            <h4 class="one"  @click="showData('show1')"><font-awesome-icon icon="fa-solid fa-user-tie" /></h4>
                            </div>
                            <div class="about-us-icon-b about-us-icon" :class="show == 'show2' ? 'active' : ''">
                            <h4 class="one" @click="showData('show2')"><font-awesome-icon icon="fa-solid fa-gears" /></h4>
                            </div>
                            <div class="about-us-icon-c about-us-icon" :class="show == 'show3' ? 'active' : ''">
                            <h4 class="one" @click="showData('show3')"><font-awesome-icon icon="fa-solid fa-comments" /></h4>
                            </div>
                            <div class="about-us-icon-d about-us-icon" :class="show == 'show4' ? 'active' : ''">
                            <h4 class="one" @click="showData('show4')"><font-awesome-icon icon="fa-solid fa-flag" /></h4>
                            </div>
                            <div class="about-us-icon-e about-us-icon" :class="show == 'show5' ? 'active' : ''">
                            <h4 class="one" @click="showData('show5')"><font-awesome-icon icon="fa-solid fa-briefcase" /></h4>
                            </div>
                        </div>
                        <div class="about-us-main">
                            <h4 v-for="(feature, index) in features.find(one => one.key === 'features_text_list').value.slice(0, 5)" :key="index" class="about-us-main-icon">
                                <div v-if="show == `show${index+1}`" class="about-us-main-content">
                                    <font-awesome-icon icon="fa-solid fa-user-tie" />
                                    <h2>
                                        {{feature.title}}
                                    </h2>

                                    <h3>
                                        {{feature.description}}
                                    </h3>
                                </div>
                            </h4>
                        </div>
                    </div>

                </div>
                



            </div>

        </div>
    </section>
</template>

<script>

export default {
    name: 'AppHomeWhy',
    props: ["features"],
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

<style lang="scss">
.about-sec {
    padding: 30px;
}
.about-icon {
    display: inline-block;
    border: 3px solid var(--main-color);
    border-radius: 50px;
    display: grid;
    place-content: center;
    width: 30px;
    height: 30px;
    font-size: 0.8rem;
}
    .about-us {
        height: 442px !important;
        width: 452px !important;
        max-width: 450px !important;
        border: 5px solid rgb(21, 26, 99) !important;
        @include xs {
            height: 300px !important;
            width: 300px !important;
        }
    }
    .about-us .one {
        font-size: 25px !important;
        padding: 5px !important;
    }
    .about-us-icon {
        background: rgb(36, 177, 238) !important;
    }
    .about-us-icon-a {
        top: -220px !important;
        @include xs {
            top: -150px !important;
        }
    }
    .about-us-icon-b {
        left: 210.743px !important;
        @include xs {
            left: 130.743px !important;
        }
    }
    .about-us-icon-c {
        left: 125.191px !important;
        top: 182.074px !important;
        @include xs {
            left: 110.191px !important;
            top: 92.074px !important;
        }
    }
    .about-us-icon-d {
        left: -125.191px !important;
        top: 182.074px !important;
        @include xs {
            left: -110.191px !important;
            top: 95.074px !important;
        }
    }
    .about-us-icon-e {
        left: -210.743px !important;
        @include xs {
            left: -130.743px !important;
        }
    }

    .about-us-icon .one {
        padding: 9px !important;
        margin: 0 !important;
    }
    .about-us-icon.active::after {
        content: '';
        position: absolute;
        z-index: -1;
        top: 0;
        right: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: transparent;
        border: 1px solid #0071dc;
        border-radius: 50px;
        -webkit-animation: ripple 2s infinite ease-in-out;
        animation: ripple 2s infinite ease-in-out;
    }
    .about-us-main {
        background-color: rgb(21, 26, 99) !important;
        color: #fff !important;
    }
    .about-us-main-icon {
        @include xs {
            margin: 0;
        }
    }
    .aboutus {
        h3 {
            display: flex;
            justify-content: flex-end;
            margin-bottom: 30px;
        }
    }
    .about-item {
        display: flex;
        gap: 10px;
        justify-content: flex-end;
    }
    @keyframes circle_pop {
        0%,
        100% {
        transform:scale3d(1,1,1)
        }
        50% {
        transform:scale3d(1.3,1.3,1.3)
        }
    }
</style>
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
                        <div class="about-item mb-20 d-flex">
                            
                            <div class="about-icon">
                                <font-awesome-icon icon="fa-solid fa-1" />
                            </div>
                            <div class="about-details">
                                <p> Because acting with lorm ipsum integrity ipsum porta maximus, odio augue ullam
                                    rutrum velit sit tincidunt elit.</p>

                            </div>
                        </div>
                        <div class="about-item mb-20 d-flex">
                            
                            <div class="about-icon">
                                <font-awesome-icon icon="fa-solid fa-2" />
                                
                            </div>
                            <div class="about-details">
                                <p> Because acting with lorm ipsum integrity ipsum porta maximus, odio augue ullam
                                    rutrum velit sit tincidunt elit.</p>

                            </div>
                        </div>
                        <div class="about-item mb-20 d-flex">
                            
                            <div class="about-icon">
                                <font-awesome-icon icon="fa-solid fa-3" />
                                
                            </div>
                            <div class="about-details">
                                <p> Because acting with lorm ipsum integrity ipsum porta maximus, odio augue ullam
                                    rutrum velit sit tincidunt elit.</p>

                            </div>
                        </div>
                        <div class="about-item mb-20 d-flex">
                            
                            <div class="about-icon">
                                <font-awesome-icon icon="fa-solid fa-4" />
                                
                            </div>
                            <div class="about-details">
                                <p> Because acting with lorm ipsum integrity ipsum porta maximus, odio augue ullam
                                    rutrum velit sit tincidunt elit.</p>

                            </div>
                        </div>
                        <div class="about-item mb-20 d-flex">
                            
                            <div class="about-icon">
                                <font-awesome-icon icon="fa-solid fa-5" />
                                
                            </div>
                            <div class="about-details">
                                <p> Because acting with lorm ipsum integrity ipsum porta maximus, odio augue ullam
                                    rutrum velit sit tincidunt elit.</p>

                            </div>
                        </div>
                        <div class="about-item mb-20 d-flex">
                            
                            <div class="about-icon">
                                <font-awesome-icon icon="fa-solid fa-6" />
                                
                            </div>
                            <div class="about-details">
                                <p> Because acting with lorm ipsum integrity ipsum porta maximus, odio augue ullam
                                    rutrum velit sit tincidunt elit.</p>

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
                            <h4 class="about-us-main-icon">
                                <div v-if="show == 'show1'" class="about-us-main-content">
                                    <font-awesome-icon icon="fa-solid fa-user-tie" />
                                    <h2>
                                        BRILLIANT TEAM
                                    </h2>

                                    <h3>
                                        Nunc facilisis mauris id luctus nunc amet lacus faucibus lorem.
                                    </h3>
                                </div>
                            </h4>
                            <h4 class="about-us-main-icon">
                                <div v-if="show == 'show2'" class="about-us-main-content">
                                    <font-awesome-icon icon="fa-solid fa-gears" />
                                    <h2>
                                        Creative & Professional
                                    </h2>

                                    <h3>
                                        Pellen tesque habitant morbi tristique amet glavrida senectu.
                                    </h3>
                                </div>
                            </h4>
                            <h4 class="about-us-main-icon">
                                <div v-if="show == 'show3'" class="about-us-main-content">
                                    <font-awesome-icon icon="fa-solid fa-comments" />
                                    <h2>
                                        Complex Sollutions
                                    </h2>

                                    <h3>
                                        Lorem ipsum – tesque morbi dolor for nulla tristique senectu.
                                    </h3>
                                </div>
                            </h4>
                            <h4 class="about-us-main-icon">
                                <div v-if="show == 'show4'" class="about-us-main-content">
                                    <font-awesome-icon icon="fa-solid fa-flag" />
                                    <h2>
                                        100% Result Guarantee
                                    </h2>

                                    <h3>
                                        Dolor glavrida amet habitant morbi dolor agalvida – for tristique lorem senectu.
                                    </h3>
                                </div>
                            </h4>
                            <h4 class="about-us-main-icon">
                                <div v-if="show == 'show5'" class="about-us-main-content">
                                    <font-awesome-icon icon="fa-solid fa-briefcase" />
                                    <h2>
                                        Industry Experience
                                    </h2>

                                    <h3>
                                        Nullam faucibus dictum nibh vel tempor – at loem ipsum dapibus!
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
    padding: 0px 8px;
    height: max-content;
    border-radius: 50px;
    margin-right: 15px;
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
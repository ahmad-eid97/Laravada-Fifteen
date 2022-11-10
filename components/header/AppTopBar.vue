<template>
    <div class="bg-main top_nav">
        <div class="subnav-conatiner d-flex align-items-center justify-content-between text-light  reponsive-justify-content">
            <div class="d-flex fw-bold">
                <p>
                <span class="mx-1"> 
                    <font-awesome-icon icon="fa-solid fa-phone" />
                </span>

                011 322 44 56
                </p>
                <p>
                <span class="mx-1">
                    <font-awesome-icon icon="fa-solid fa-location-dot" />
                </span>

                011 322 44 56 Highland St. Tonawanda, NY 14150
                </p>
            </div>
            <div class="d-flex">

                <form class="searchform mini-widget-searchform">
                    <input type="text" class="field searchform-s" name="s" value="" placeholder="Search..." title="Search form">
                    <a href="" class="search-icon"><font-awesome-icon icon="fa-solid fa-magnifying-glass" /></a>
                </form>
                <div class="soc-ico">
                    <a title="Facebook page opens in new window" href="/" target="_blank" class="facebook">
                        <font-awesome-icon icon="fa-brands fa-facebook-f" />
                    </a>
                    <a title="Twitter page opens in new window" href="/" target="_blank" class="twitter">
                        <font-awesome-icon icon="fa-brands fa-twitter" />
                    </a>
                    <a title="Dribbble page opens in new window" href="/" target="_blank" class="dribbble">
                        <font-awesome-icon icon="fa-brands fa-dribbble" />
                    </a>
                </div>
                <lang-switch></lang-switch>
            </div>
        </div>
    </div>
</template>

<script>
import LangSwitch from '../langSwitch/langSwitch.vue'
export default {
    name: 'AppTopBar',
    components: {
        LangSwitch
    },
    data() {
        return {

        }
    },
    mounted() {
    },
    methods: {

    }
}
</script>
<style scoped lang="scss">
    .top_nav {
        background-color: var(--secondary-color);
        @include sm {
            display: none;
        }
    }
    .subnav-conatiner {
        padding: 4px 20px;
    }
    .subnav-conatiner p {
        margin: 0 10px 0 0;
    }
    .subnav-conatiner p:last-of-type {
        margin: 0 0 0 10px;
    }
    .subnav-conatiner .searchform {
        position: relative;
        z-index: 3;
        max-width: 100%;
        margin-right: 10px;
    }
    .subnav-conatiner .searchform input[type="text"]{
        color: #fff;
        min-height: 28px;
        height: auto;
        line-height: 28px;
        width: 120px;
        border-width: 2px;
        border-color: rgba(255,255,255,.25);
        border-radius: 100px;
        background: transparent;
        padding: 0 15px;
        transition: width .55s ease;
        max-width: 100%;
        border-style: solid;
        box-sizing: border-box;
    }
    .subnav-conatiner .searchform input[type="text"]::placeholder {
        color: #fff !important;
        opacity: 1;
    }
    .subnav-conatiner .searchform input[type="text"]:hover ,
    .subnav-conatiner .searchform input[type="text"]:focus {
        width: 200px;
        outline: 0;
    }
    .subnav-conatiner .searchform a {
        color: #fff;
        right: 15px;
        width: 16px;
        position: absolute;
        justify-content: center;
        top: 0;
        height: 100%;
    }
    .subnav-conatiner .searchform a svg {
        vertical-align: middle;
    }
    .subnav-conatiner .soc-ico {
        margin-left: 10px;
    }
    .subnav-conatiner .soc-ico a  {
        width: 30px;
        height: 30px;
        margin: 0 2px 0 0;
        line-height: 30px;
        border-radius: 100px;
        color: #fff;
        position: relative;
        box-shadow: inset 0 0 0 2px rgba(255,255,255,.32);
        display: inline-block;
        text-align: center;
    }
    svg {
        max-width: 15px !important;
    }
</style>
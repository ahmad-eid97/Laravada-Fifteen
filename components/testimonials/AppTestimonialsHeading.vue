<template>
    <div class="heading">
        <div class="row justify-content-center m-0">
            <h3 class="col-12 text-center title">
                Testimonials
            </h3>
            <div class="col-12 text-center">
                <div class="breadcrumb">
                    <router-link to="home">
                        Home
                    </router-link>
                    <a href="">
                        <font-awesome-icon icon="fa-solid fa-angles-right" />
                    </a>
                    <a href="#">
                        Testimonials
                    </a>
                </div>
            </div>
        </div>
        
    </div>
</template>

<script>
export default {
    name: 'AppTestimonialsHeading',


}
</script>

<style>
.heading {
    padding-top: 150px;
    padding-bottom: 150px;
    position: relative;
    z-index: 1;
    background: var(--gradient-background);
}
.heading h3 {
    font-size: 45px;
    color: #fff;
    font-weight: 600;
    position: relative;
}
.heading .breadcrumb {
    display: flex;
    justify-content: center;
}
.heading a{
    font-size: 18px;
    font-weight: 400;
    line-height: 28.8px;
    color: #fff;
    text-decoration: none;
    display: inline-block;
    margin: 0 10px;
}
.heading a:hover {
    color: #091426;
}
</style>
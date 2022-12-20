<template>
  <header class="header header-style-2 clearfix">
    <app-top-bar></app-top-bar>
    <b-navbar
      toggleable="lg"
      :class="{ onScroll: !topOfPage }"
      class="navbar navbar-expand-lg navbar-light py-0"
    >
      <b-navbar-brand :href="localePath('/')"
        ><img
          src="/assets/images/logo.png"
          alt="logo"
          style="width: 150px; margin: 10px 0"
      /></b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <ul class="navbar-nav me-auto">
          <li class="nav-item">
            <nuxt-link
              class="nav-link"
              active-class="active"
              aria-current="page"
              :to="localePath('/')"
              exact
              >Home</nuxt-link
            >
          </li>

          <li class="nav-item dropdown">
            <dropdown-menu
              v-model="show"
              :hover="true"
              :closeOnClickOutside="true"
              :hover_time="10"
            >
              <nuxt-link
                class="nav-link dropdown-toggle"
                active-class="active"
                :to="localePath('/about')"
                id="navbarDropdownMenuLink"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
              >
                About Us
              </nuxt-link>
              <div slot="dropdown">
                <a class="dropdown-item" href="#">dropdown link</a>
                <a class="dropdown-item" href="#">dropdown link</a>
                <a class="dropdown-item" href="#">dropdown link</a>
              </div>
            </dropdown-menu>
          </li>

          <li class="nav-item dropdown">
            <dropdown-menu
              v-model="show1"
              :hover="true"
              :closeOnClickOutside="true"
              :hover_time="10"
            >
              <nuxt-link
                class="nav-link dropdown-toggle"
                active-class="active"
                :to="localePath('/services')"
                id="navbarDropdownMenuLink"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
              >
                Services
              </nuxt-link>
              <div slot="dropdown">
                <a class="dropdown-item" href="#">dropdown link</a>
                <a class="dropdown-item" href="#">dropdown link</a>
                <a class="dropdown-item" href="#">dropdown link</a>
              </div>
            </dropdown-menu>
          </li>

          <li class="nav-item">
            <nuxt-link
              class="nav-link"
              active-class="active"
              :to="localePath('/testimonials')"
              >Testimmonials</nuxt-link
            >
          </li>
          <li class="nav-item">
            <nuxt-link
              class="nav-link"
              active-class="active"
              :to="localePath('/blogs')"
              >Blogs</nuxt-link
            >
          </li>
          <li class="nav-item">
            <nuxt-link
              class="nav-link"
              active-class="active"
              :to="localePath('/contact')"
              >Contact</nuxt-link
            >
          </li>
          <li class="nav-item">
            <nuxt-link
              class="nav-link"
              active-class="active"
              aria-current="page"
              :to="localePath('/careers')"
              exact
              >Career</nuxt-link
            >
          </li>
          <li class="nav-item">
            <nuxt-link
              class="nav-link"
              active-class="active"
              aria-current="page"
              :to="localePath('/events')"
              exact
              >Events</nuxt-link
            >
          </li>
        </ul>

        <div class="btn-container">
          <button class="btn nav-btn fw-bold">
            Start a project <i class="bi bi-arrow-right-circle-fill mx-2"></i>
          </button>
          <div v-if="$store.state.user" class="logout" @click="logout">
            <i class="fa-regular fa-right-from-bracket"></i>
          </div>
        </div>
      </b-collapse>
    </b-navbar>
  </header>
</template>

<script>
import AppTopBar from "./AppTopBar.vue";
import DropdownMenu from "@innologica/vue-dropdown-menu";
export default {
  name: "AppHeader",
  components: {
    AppTopBar,
    DropdownMenu,
  },
  data() {
    return {
      show: false,
      show1: false,
      topOfPage: true,
    };
  },
  beforeMount() {
    window.addEventListener("scroll", this.handleScroll);
  },
  mounted() {},
  methods: {
    logout() {
      this.$store.commit("setUserData", null);
      this.$cookies.remove("cms-auth");
      this.$cookies.remove("cms-user");
      this.$router.push(this.localePath("/login"));
    },
    handleScroll() {
      if (window.pageYOffset > 200) {
        if (this.topOfPage) this.topOfPage = false;
      } else {
        if (!this.topOfPage) this.topOfPage = true;
      }
    },
  },
};
</script>
<style lang="scss">
.onScroll {
  position: fixed;
  width: 100%;
  display: flex;
  align-items: center;
  transition: all 0.2s ease-in-out;
  box-shadow: 0 0 10px #aaa;
  background-color: #fff;
  top: 0;
  z-index: 10;
}
.logout {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: var(--main-color);
  color: #fff;
  display: grid;
  place-items: center;
  font-size: 1.2rem;
  cursor: pointer;
}
.navbar {
  padding-right: 20px;
  padding-left: 20px;
}
.navbar-nav .nav-link {
  padding-right: 20px !important;
  padding-left: 20px !important;
  font-weight: bold;
  height: 100%;
}
.dropdown {
  min-height: 80px;
  @include sm {
    min-height: 40px;
  }
}
.dropdown .nav-link {
  min-height: 80px;
  @include sm {
    min-height: 40px;
  }
}
.navbar .dropdown-menu {
  border-radius: 0;
  background-color: #fff;
  padding: 10px;
  width: 280px;
  padding: 10px;
  box-shadow: 0 0 4px rgba(0, 0, 0, 0.2);
  box-sizing: border-box;
}
.navbar .dropdown-menu a {
  margin: 0 0 1px;
  padding: 12px;
}
.navbar .dropdown-menu a:hover {
  background-color: rgba(31, 169, 229, 0.1);
  color: var(--secondary-color);
}
</style>

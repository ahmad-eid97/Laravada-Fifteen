<template>
  <header class="header header-style-2 clearfix">
    <div class="cart" :class="openCart ? 'opened' : ''">
      <div class="head">
        <i class="fa-regular fa-xmark" @click="openCart = false"></i>
        <button
          @click="goToCheckout"
          :disabled="$store.state.cartItems.length <= 0"
        >
          <i class="fa-regular fa-badge-check"></i> Checkout
        </button>
      </div>
      <cart />
    </div>
    <app-top-bar></app-top-bar>
    <b-navbar
      toggleable="lg"
      :class="{ onScroll: !topOfPage }"
      class="navbar navbar-expand-lg navbar-light"
    >
      <b-navbar-brand :href="localePath('/')"
        ><img
          src="/assets/images/logo.png"
          alt="logo"
          style="width: 150px; margin: 10px 0"
      /></b-navbar-brand>
      <div class="btn-container smallScr">
        <div class="m-0 cartIcon" @click="openCart = !openCart">
          <span>{{ $store.state.cartItems.length }}</span>
          <i class="fa-regular fa-cart-plus"></i>
        </div>
        <div v-if="$store.state.user" class="logout" @click="logout">
          <i class="fa-regular fa-right-from-bracket"></i>
        </div>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      </div>
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
          <li class="nav-item outLarge">
            <nuxt-link
              class="nav-link"
              active-class="active"
              aria-current="page"
              :to="localePath('/login')"
              v-if="$store.state.user"
              @click="logout"
              exact
              >Logout</nuxt-link
            >
          </li>
        </ul>
      </b-collapse>
      <div class="btn-container largeScr">
        <div class="m-0 cartIcon" @click="openCart = !openCart">
          <span>{{ $store.state.cartItems.length }}</span>
          <i class="fa-regular fa-cart-plus"></i>
        </div>
        <div v-if="$store.state.user" class="logout" @click="logout">
          <i class="fa-regular fa-right-from-bracket"></i>
        </div>
      </div>
    </b-navbar>
  </header>
</template>

<script>
import cart from "../cart/cart.vue";
import AppTopBar from "./AppTopBar.vue";
import DropdownMenu from "@innologica/vue-dropdown-menu";
export default {
  name: "AppHeader",
  components: {
    AppTopBar,
    DropdownMenu,
    cart,
  },
  data() {
    return {
      show: false,
      show1: false,
      topOfPage: true,
      openCart: false,
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
    goToCheckout() {
      this.openCart = false;
      this.$router.push("/checkout");
    },
  },
};
</script>
<style lang="scss">
nav {
  padding: 10px 20px !important;
}
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
.cart {
  width: 390px;
  height: 100vh;
  position: fixed;
  top: 0;
  right: 0;
  transform: translateX(390px);
  background-color: #fff;
  z-index: 999999;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
  .head {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px;
    & > i {
      border: 1px solid var(--main-color);
      border-radius: 5px;
      width: 30px;
      height: 30px;
      display: grid;
      place-items: center;
      cursor: pointer;
      background-color: var(--main-color);
      color: #fff;
      &:hover {
        color: var(--main-color);
        background: transparent;
      }
    }
    button {
      padding: 5px 30px;
      font-size: 1.1rem;
      background-color: var(--main-color);
      color: #fff;
      border: 1px solid var(--main-color);
      display: flex;
      align-items: center;
      gap: 5px;
      i {
        font-size: 1.1rem;
      }
      &:disabled {
        opacity: 0.5;
        cursor: not-allowed;
        &:hover {
          background-color: var(--main-color);
          color: #fff;
        }
      }
      &:hover {
        background-color: transparent;
        color: var(--main-color);
      }
    }
  }
  &.opened {
    transform: translateX(0);
  }
  @include xs {
    width: 350px;
  }
}
.cartIcon {
  border: 1px solid var(--main-color);
  border-radius: 5px;
  width: 45px;
  height: 45px;
  display: grid;
  place-items: center;
  cursor: pointer;
  position: relative;
  margin: 0 10px !important;
  span {
    position: absolute;
    top: -15px;
    right: -10px;
    width: 30px;
    height: 30px;
    background-color: var(--main-color);
    border-radius: 50%;
    color: #fff;
    display: grid;
    place-content: center;
    font-size: 1.1rem;
    @include sm {
      font-size: 1rem;
    }
  }
  i {
    color: var(--main-color);
  }
  @include sm {
    width: 40px;
    height: 40px;
    margin: 0 10px !important;
  }
  &:hover {
    background-color: var(--main-color);
    border-color: var(--main-color);
    i {
      color: #fff;
    }
  }
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
  @include md {
    display: none;
  }
}
.outLarge {
  display: none;
  @include md {
    display: inline;
  }
}
.smallScr {
  align-items: center;
  display: none;
  @include md {
    display: flex;
  }
}
.largeScr {
  align-items: center;
  display: flex;
  @include md {
    display: none;
  }
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
  /* min-height: 80px; */
  @include sm {
    /* min-height: 40px; */
  }
}
.navbar-toggler {
  box-shadow: none !important;
  margin: 0;
}
.dropdown .nav-link {
  /* min-height: 80px; */
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

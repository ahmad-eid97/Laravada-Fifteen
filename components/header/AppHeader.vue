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
        <b-navbar-nav class="align-items-center">
          <b-nav-item
            active-class="active"
            :to="localePath(`/${item.link}`)"
            exact
            v-for="item in $store.state.topMenu"
            :key="item.id"
          >
            <span v-if="!item.child.length">{{ item.label }}</span>

            <b-dropdown
              :text="item.label"
              block
              class="m-2 dropdownBtn"
              v-if="item.child.length"
            >
              <b-dropdown-item
                v-for="child in item.child"
                :key="child.id"
                :to="localePath('/' + child.link)"
                >{{ child.label }}</b-dropdown-item
              >
            </b-dropdown>
          </b-nav-item>
          <b-nav-item v-if="$store.state.user" @click="logout" class="outLarge">
            Logout
          </b-nav-item>
        </b-navbar-nav>
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
      this.$swal({
        title: "Logout!",
        text: "Are you sure? You want to logout from your account!",
        type: "warning",
        showCancelButton: true,
        confirmButtonColor: "#ff5e57",
        confirmButtonText: "Logout",
      }).then((result) => {
        if (result.value) {
          this.confirmLogout();
        }
      });
    },
    confirmLogout() {
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
.swal2-container {
  padding: 0 !important;
}
.swal2-shown {
  padding: 0 !important;
}
.swal2-confirm:focus,
.swal2-cancel:focus {
  box-shadow: none !important;
}
.swal2-cancel {
  background: #e5e5e5 !important;
  color: rgb(51, 51, 51) !important;
}
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
.nav-item {
  & > .dropdown {
    display: none;
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
.dropdownBtn {
  margin: 0 !important;
  button {
    background: none !important;
    padding: 0 !important;
    text-transform: none !important;
    font-size: 1.1rem !important;
    font-family: unset !important;
    font-weight: 700 !important;
    box-shadow: none !important;
    border: none !important;
    min-width: unset !important;
    width: 100%;
    min-height: 30px;
    position: relative;
    top: -3px;
    color: #000;
    position: relative;
    top: 0px;
    margin: 0 !important;
    &:hover {
      color: #000;
    }
  }
  .dropdown-menu {
    top: 40px !important;
  }
}
</style>

<template>
  <div class="bg-main top_nav">
    <div
      class="subnav-conatiner d-flex align-items-center justify-content-between text-light reponsive-justify-content"
    >
      <div class="d-flex fw-bold info">
        <p>
          <span class="mx-1">
            <i class="fa-solid fa-phone"></i>
          </span>

          {{
            $store.state.websiteSettings.find(
              (one) => one.key === "contact_phone"
            ).plain_value
          }}
        </p>
        <p>
          <span class="mx-1">
            <i class="fa-solid fa-location-dot"></i>
          </span>

          {{
            $store.state.websiteSettings.find(
              (one) => one.key === "contact_address"
            ).plain_value
          }}
        </p>
      </div>
      <div class="d-flex">
        <form
          class="searchform mini-widget-searchform"
          :class="$i18n.locale === 'ar' ? 'arabic' : ''"
        >
          <input
            type="text"
            class="field searchform-s"
            name="s"
            value=""
            placeholder="Search..."
            title="Search form"
          />
          <a href="" class="search-icon"
            ><i class="fa-solid fa-magnifying-glass"></i
          ></a>
        </form>
        <div class="soc-ico">
          <a
            title="Facebook page opens in new window"
            href="/"
            target="_blank"
            class="facebook"
          >
            <i class="fa-brands fa-facebook-f"></i>
          </a>
          <a
            title="Twitter page opens in new window"
            href="/"
            target="_blank"
            class="twitter"
          >
            <i class="fa-brands fa-twitter"></i>
          </a>
          <a
            title="Dribbble page opens in new window"
            href="/"
            target="_blank"
            class="dribbble"
          >
            <i class="fa-brands fa-dribbble"></i>
          </a>
        </div>
        <lang-switch></lang-switch>
      </div>
    </div>
  </div>
</template>

<script>
import LangSwitch from "../langSwitch/langSwitch.vue";
export default {
  name: "AppTopBar",
  components: {
    LangSwitch,
  },
  data() {
    return {};
  },
  mounted() {},
  methods: {},
};
</script>
<style lang="scss">
.top_nav {
  background-color: var(--secondary-color);
  /* @include sm {
    display: none;
  } */
}
.top_nav .info {
  display: flex !important;
  @include md {
    display: none !important;
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
.subnav-conatiner .searchform input[type="text"] {
  color: #fff;
  min-height: 28px;
  height: auto;
  line-height: 28px;
  width: 120px;
  border-width: 2px;
  border-color: rgba(255, 255, 255, 0.25);
  border-radius: 100px;
  background: transparent;
  padding: 0 15px;
  transition: width 0.55s ease;
  max-width: 100%;
  border-style: solid;
  box-sizing: border-box;
}
.subnav-conatiner .searchform input[type="text"]::placeholder {
  color: #fff !important;
  opacity: 1;
}
.subnav-conatiner .searchform input[type="text"]:hover,
.subnav-conatiner .searchform input[type="text"]:focus {
  width: 200px;
  outline: 0;
}
.subnav-conatiner .searchform a {
  color: #fff;
  right: 10px;
  width: 16px;
  position: absolute;
  justify-content: center;
  top: 2px;
  height: 100%;
}
.subnav-conatiner .searchform.arabic a {
  right: unset;
  left: 10px;
}
.subnav-conatiner .searchform a i {
  vertical-align: middle;
}
.subnav-conatiner .soc-ico {
  margin-left: 10px;
}
.subnav-conatiner .soc-ico a {
  width: 30px;
  height: 30px;
  margin: 0 2px 0 0;
  line-height: 30px;
  border-radius: 100px;
  color: #fff;
  position: relative;
  box-shadow: inset 0 0 0 2px rgba(255, 255, 255, 0.32);
  display: inline-block;
  text-align: center;
}
.top_nav i {
  max-width: 15px !important;
}
</style>

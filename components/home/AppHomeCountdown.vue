<template>
  <section class="counter-area">
    <div class="container">
      <div class="section-title text-center">
        <span class="sp-color2">Numbers Are Talking</span>
        <h2>Let’s Check Our Business Growth and Success Story</h2>
        <p>
          Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat
          ipsum, nec sagittis sem nibh id elit. Duis sed odio sit amet nibh
          vulputate cursus a sit amet mauris Morbi accumsan ipsum velit.
        </p>
      </div>
      <div
        class="row pt-45"
        v-if="counter.find((one) => one.key === 'counter_success_list').value"
      >
        <div
          v-for="item in counter.find(
            (one) => one.key === 'counter_success_list'
          ).value"
          :key="item"
          class="col-lg-3 col-md-3 col-sm-6"
        >
          <div class="counter-another-content">
            <i :class="item.icon"></i>
            <div>
              <h3>
                <VueJsCounter
                  class="d-inline"
                  :startVal="0"
                  :endVal="item.counter"
                  separator=","
                ></VueJsCounter
                >+
              </h3>
              <span>{{ item.title }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import VueJsCounter from "vue-count-to";
export default {
  name: "AppHomeCountdown",
  props: ["counter"],
  components: {
    VueJsCounter,
  },
  data() {
    return {};
  },
  methods: {},
  mounted() {
    document
      .querySelector(".counter-area")
      .style.setProperty(
        "--counter-bg",
        this.counter.find(
          (one) => one.key === "counter_success_background_active_section"
        ).value === "color"
          ? this.counter.find(
              (one) => one.key === "counter_success_background_color_section"
            ).value
          : `url(${
              this.counter.find(
                (one) => one.key === "counter_success_background_image_section"
              ).value
            })`
      );

    document
      .querySelector(".counter-area")
      .style.setProperty(
        "--counter-fontSize",
        `${
          this.counter.find(
            (one) => one.key === "counter_success_font_size_section"
          ).value
        }px`
      );

    if (
      this.counter.find(
        (one) => one.key === "counter_success_border_position_section"
      ) &&
      this.counter.find(
        (one) => one.key === "counter_success_border_position_section"
      ).value === "both"
    ) {
      document
        .querySelector(".counter-area")
        .style.setProperty(
          "--counter-border-top",
          `${
            this.counter.find(
              (one) => one.key === "counter_success_border_size_section"
            ).value
          }px ${
            this.counter.find(
              (one) => one.key === "counter_success_border_type_section"
            ).value
          } ${
            this.counter.find(
              (one) => one.key === "counter_success_border_color_section"
            ).value
          }`
        );

      document
        .querySelector(".counter-area")
        .style.setProperty(
          "--counter-border-bottom",
          `${
            this.counter.find(
              (one) => one.key === "counter_success_border_size_section"
            ).value
          }px ${
            this.counter.find(
              (one) => one.key === "counter_success_border_type_section"
            ).value
          } ${
            this.counter.find(
              (one) => one.key === "counter_success_border_color_section"
            ).value
          }`
        );
    } else if (
      this.counter.find(
        (one) => one.key === "counter_success_border_position_section"
      ) &&
      this.counter.find(
        (one) => one.key === "counter_success_border_position_section"
      ).value === "top"
    ) {
      document
        .querySelector(".counter-area")
        .style.setProperty(
          "--counter-border-top",
          `${
            this.counter.find(
              (one) => one.key === "counter_success_border_size_section"
            ).value
          }px ${
            this.counter.find(
              (one) => one.key === "counter_success_border_type_section"
            ).value
          } ${
            this.counter.find(
              (one) => one.key === "counter_success_border_color_section"
            ).value
          }`
        );
    } else if (
      this.counter.find(
        (one) => one.key === "counter_success_border_position_section"
      ) &&
      this.counter.find(
        (one) => one.key === "counter_success_border_position_section"
      ).value === "bottom"
    ) {
      document
        .querySelector(".counter-area")
        .style.setProperty(
          "--counter-border-bottom",
          `${
            this.counter.find(
              (one) => one.key === "counter_success_border_size_section"
            ).value
          }px ${
            this.counter.find(
              (one) => one.key === "counter_success_border_type_section"
            ).value
          } ${
            this.counter.find(
              (one) => one.key === "counter_success_border_color_section"
            ).value
          }`
        );
    }
  },
};
</script>
<style lang="scss">
.counter-area {
  padding: 100px 0 70px;

  --counter-bg: #fff;
  --counter-fontSize: 20px;
  --counter-border-top: 0px solid #fff;
  --counter-border-bottom: 0px solid #fff;

  background: var(--counter-bg);
  border-top: var(--counter-border-top);
  border-bottom: var(--counter-border-bottom);
  background-repeat: no-repeat;
  background-size: cover;
  padding: 50px 0 0 0;

  h2 {
    font-size: var(--counter-fontSize) !important;
    text-align: center;
  }
}
.section-title span {
  margin-bottom: 8px;
  font-weight: 600;
  display: block;
}
.sp-color2 {
  color: var(--main-color) !important;
}
.counter-area .section-title h2 {
  max-width: 560px;
  margin-left: auto;
  margin-right: auto;
}
.section-title h2 {
  /* font-size: 35px; */
  font-weight: 600;
  margin-top: 0;
  line-height: 1.2;
  color: #252525;
  margin-bottom: 0;
}
.counter-area .section-title p {
  margin-left: auto;
  margin-right: auto;
  max-width: 720px;
}
.section-title p {
  padding-top: 10px;
  margin-bottom: 0;
  max-width: 530px;
  color: #444;
}
.pt-45 {
  padding-top: 45px;
}
.counter-another-content {
  margin-bottom: 25px;
  padding-left: 90px;
  position: relative;
}
.counter-another-content h3 {
  color: #252525;
  font-size: 35px;
  line-height: 1;
  margin-bottom: 8px;
}

.counter-another-content h3 span {
  color: #252525;
  font-size: 35px;
  line-height: 1;
  margin-bottom: 8px;
}
.counter-another-content span {
  font-size: 17px;
  color: #444;
  margin-bottom: 0;
  font-weight: 600;
}
.counter-another-content i {
  position: absolute;
  line-height: 1;
  font-size: 60px;
  top: 3px;
  left: 0;
  color: var(--main-color);
}
@include md {
  .counter-another-content {
    padding: 0 !important;
  }
  .counter-another-content h3 span {
    font-size: 25px;
  }
  .counter-another-content i {
    font-size: 50px;
    position: relative;
  }
}

@include sm {
  .counter-another-content {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    padding: 0 !important;
  }
  .counter-another-content h3 span {
    font-size: 27px;
  }
  .counter-another-content i {
    font-size: 50px;
    position: relative;
  }
}

@include xs {
  .counter-another-content {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    padding: 0 !important;
  }
  .counter-another-content h3 span {
    font-size: 20px;
  }
  .counter-another-content i {
    font-size: 40px;
    position: relative;
  }
}
</style>

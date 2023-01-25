<template>
  <section class="technology-area">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-6">
          <div class="technology-right">
            <div class="section-title">
              <span class="sp-color2">Technology Index</span>
              <h2>
                {{
                  solutions.find((one) => one.key === "solutions_title").value
                }}
              </h2>
              <p>
                {{
                  solutions.find((one) => one.key === "solutions_description")
                    .value
                }}
              </p>
            </div>
            <div
              class="row justify-content-center"
              v-if="solutions.find((one) => one.key === 'solutions_list').value"
            >
              <div
                v-for="item in solutions.find(
                  (one) => one.key === 'solutions_list'
                ).value"
                :key="item"
                class="col-lg-3 col-6 col-sm-3"
              >
                <div class="technology-item">
                  <i :class="item.icon"></i>
                  <h3>{{ item.title }}</h3>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="col-lg-6">
          <div class="technology-play-area">
            <iframe
              width="560"
              height="315"
              src="https://www.youtube.com/embed/tUP5S4YdEJo"
              title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeTechnology",
  props: ["solutions"],
  components: {},
  data() {
    return {};
  },
  methods: {},
  mounted() {
    document
      .querySelector(".technology-area")
      .style.setProperty(
        "--solutions-bg",
        this.solutions.find(
          (one) => one.key === "solutions_background_active_section"
        ).value === "color"
          ? this.solutions.find(
              (one) => one.key === "solutions_background_color_section"
            ).value
          : `url(${
              this.solutions.find(
                (one) => one.key === "solutions_background_image_section"
              ).value
            })`
      );

    document
      .querySelector(".technology-area")
      .style.setProperty(
        "--solutions-fontSize",
        `${
          this.solutions.find(
            (one) => one.key === "solutions_font_size_section"
          ).value
        }px`
      );

    if (
      this.solutions.find(
        (one) => one.key === "solutions_border_position_section"
      ) &&
      this.solutions.find(
        (one) => one.key === "solutions_border_position_section"
      ).value === "both"
    ) {
      document
        .querySelector(".technology-area")
        .style.setProperty(
          "--solutions-border-top",
          `${
            this.solutions.find(
              (one) => one.key === "solutions_border_size_section"
            ).value
          }px ${
            this.solutions.find(
              (one) => one.key === "solutions_border_type_section"
            ).value
          } ${
            this.solutions.find(
              (one) => one.key === "solutions_border_color_section"
            ).value
          }`
        );

      document
        .querySelector(".technology-area")
        .style.setProperty(
          "--solutions-border-bottom",
          `${
            this.solutions.find(
              (one) => one.key === "solutions_border_size_section"
            ).value
          }px ${
            this.solutions.find(
              (one) => one.key === "solutions_border_type_section"
            ).value
          } ${
            this.solutions.find(
              (one) => one.key === "solutions_border_color_section"
            ).value
          }`
        );
    } else if (
      this.solutions.find(
        (one) => one.key === "solutions_border_position_section"
      ) &&
      this.solutions.find(
        (one) => one.key === "solutions_border_position_section"
      ).value === "top"
    ) {
      document
        .querySelector(".technology-area")
        .style.setProperty(
          "--solutions-border-top",
          `${
            this.solutions.find(
              (one) => one.key === "solutions_border_size_section"
            ).value
          }px ${
            this.solutions.find(
              (one) => one.key === "solutions_border_type_section"
            ).value
          } ${
            this.solutions.find(
              (one) => one.key === "solutions_border_color_section"
            ).value
          }`
        );
    } else if (
      this.solutions.find(
        (one) => one.key === "solutions_border_position_section"
      ) &&
      this.solutions.find(
        (one) => one.key === "solutions_border_position_section"
      ).value === "bottom"
    ) {
      document
        .querySelector(".technology-area")
        .style.setProperty(
          "--solutions-border-bottom",
          `${
            this.solutions.find(
              (one) => one.key === "solutions_border_size_section"
            ).value
          }px ${
            this.solutions.find(
              (one) => one.key === "solutions_border_type_section"
            ).value
          } ${
            this.solutions.find(
              (one) => one.key === "solutions_border_color_section"
            ).value
          }`
        );
    }
  },
};
</script>

<style lang="scss">
.technology-area {
  padding: 100px 0 70px;
  background-color: #f8f8f8;

  --solutions-bg: #fff;
  --solutions-fontSize: 20px;
  --solutions-border-top: 0px solid #fff;
  --solutions-border-bottom: 0px solid #fff;

  background: var(--solutions-bg);
  border-top: var(--solutions-border-top);
  border-bottom: var(--solutions-border-bottom);
  background-repeat: no-repeat;
  background-size: cover;
  h2 {
    font-size: var(--solutions-fontSize) !important;
  }
}
.technology-right {
  padding: 0 10px;
}
.section-title span {
  margin-bottom: 8px;
  font-weight: 600;
  display: block;
}
.sp-color2 {
  color: #0071dc;
}

.section-title h2 {
  font-size: 35px;
  font-weight: 600;
  margin-top: 0;
  line-height: 1.2;
  color: #252525;
  margin-bottom: 0;
}

.section-title p {
  padding-top: 10px;
  margin-bottom: 0;
  max-width: 530px;
  color: #444;
}
.technology-item {
  padding: 17px 17px 15px;
  border: 1px solid #0071dc;
  border-radius: 5px;
  text-align: center;
  margin: 15px 0 30px;
}
.technology-item h3 {
  color: #070b3b;
  margin-bottom: 0;
  margin-top: 17px;
  font-weight: 500;
  font-size: 18px;
}
.technology-item i {
  font-size: 35px;
  line-height: 1;
  color: #0071dc;
}

.technology-play-area iframe {
  animation: border-transform 15s infinite ease-in-out;
}
</style>

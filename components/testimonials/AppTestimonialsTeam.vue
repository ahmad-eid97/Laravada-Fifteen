<template>
  <div class="team-area pt-100 pb-70">
    <div class="container">
      <div class="section-title text-center">
        <span class="sp-color2">Our Team</span>
        <h2>Our Team Members</h2>
      </div>
      <div class="row pt-45 team" v-if="team.teams.length >= 1">
        <div
          v-for="member in team.teams"
          :key="member.id"
          class="col-sm-6 col-md-4 projects-col"
        >
          <div class="card">
            <div class="thumb">
              <img :src="member.image" alt="" />
              <div class="rollover"></div>
            </div>
            <div class="content">
              <h4>{{ member.name }}</h4>
              <h5>{{ member.job }}</h5>
              <h6>{{ member.description }}</h6>
              <h5>{{ member.phone }}</h5>
              <h5>{{ member.email }}</h5>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppTestimonialsTeam",
  props: ["team"],
};
</script>

<style>
.team-area .section-title {
  margin-bottom: 0;
}

.thumb {
  display: flex;
  justify-content: center;
}

.team-area img {
  animation: border-transform 15s infinite ease-in-out !important;
  margin-bottom: 15px;
  width: 80%;
  height: 200px;
  margin: 15px auto;
}

.section-title span {
  margin-bottom: 8px;
  font-weight: 600;
  display: block;
  color: #24b1ee;
}

.team-area .section-title h2 {
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
  font-size: 35px;
  font-weight: 600;
  margin-top: 0;
  line-height: 1.2;
  color: #1f365c;
  margin-bottom: 0;
}
.card {
  padding: 10px 20px;
  text-align: center !important;
  height: 100%;
}
</style>

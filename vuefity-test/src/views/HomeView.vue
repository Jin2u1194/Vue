<template>
  <div>
    <h1 class="subheading gray--text">Dashboard</h1>
    <v-main>
      <v-container>
        <!--정렬-->
        <v-row class="mb-3 ml-2">
          <v-btn small plain @click="sortBy('tit')">
            <span>by Project Title</span>
          </v-btn>
          <v-btn small plain @click="sortBy('per')">
            <span>by Person</span>
          </v-btn>
          <v-btn small plain @click="sortBy('due')">
            <span>by Due</span>
          </v-btn>
          <v-btn small plain @click="sortBy('sta')">
            <span>by State</span>
          </v-btn>
        </v-row>
        <!--프로젝트 내용-->
        <v-card
          v-for="data in projects"
          :key="data.tit"
          flat
          class="gray lighten-4"
        >
          <v-row no-gutters wrap :class="`pa-3 data ${data.sta}`">
            <!--tit-->
            <v-col cols="12" md="6">
              <div class="caption gray--text">Project Title</div>
              <div>
                {{ data.tit }}
              </div>
            </v-col>
            <!--person-->
            <v-col cols="4" sm="4" md="2">
              <div class="caption gray--text">Person</div>
              <div>
                {{ data.per }}
              </div>
            </v-col>
            <!--Due-->
            <v-col cols="8" sm="5" md="2">
              <div class="caption gray--text">Due</div>
              <div>
                {{ data.due }}
              </div>
            </v-col>
            <!--state-->
            <v-col cols="4" sm="3" md="2" class="pl-4">
              <div class="caption gray--text">State</div>
              <div :class="`${data.sta} sta`">
                {{ data.sta }}
              </div>
            </v-col>
          </v-row>
        </v-card>
      </v-container>
    </v-main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          tit: "자바GUI프로젝트",
          per: "최성진",
          due: "2021",
          sta: "complete",
        },
        {
          tit: "안드로이드 배달어플 만들어보기",
          per: "최성진, 장성훈",
          due: "2022-05-10~2022-06-20",
          sta: "complete",
        },
        {
          tit: "웹 포스기",
          per: "최성진",
          due: "2022-04-29~2022-05-07",
          sta: "complete",
        },
        {
          tit: "지도에 신호등 정보를 띄어보자",
          per: "최성진",
          due: "2023-03-01~",
          sta: "ongoing",
        },
        {
          tit: "포트폴리오 제작",
          per: "최성진",
          due: "2023-03-01~",
          sta: "ongoing",
        },
      ],
    };
  },
  methods: {
    sortBy(prop) {
      this.projects.sort((a, b) => (a[prop] < b[prop] ? -1 : 1));
    },
  },
};
</script>

<style>
.data.complete {
  border-left: 4px solid skyblue;
}
.data.ongoing {
  border-left: 4px solid orange;
}
.sta.complete {
  color: skyblue;
}
.sta.ongoing {
  color: orange;
}
</style>

<template>
  <div class="team">
    <h1 class="subheading gray--text">Team</h1>
    <v-container>
      <v-row>
        <v-col v-for="data in teams" :key="data.name" cols="12" sm="4" md="3">
          <v-card class="text-center ma-3">
            <v-responsive class="pt-6 mb-10">
              <v-avatar size="100"> <img :src="data.avatar" /> </v-avatar>
              <v-card-text>
                <div>{{ data.name }}</div>
                <div>{{ data.role }}</div>
              </v-card-text>
            </v-responsive>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      teams: [
        { name: "최성진", role: "본인", avatar: "/img/AA.jpg" },
        {
          name: "장성훈",
          role: "안드로이드 배달앱 만들기 팀원",
          avatar: "/img/AA.jpg",
        },
      ],
    };
  },
};
</script>

<template>
    <div id="footer">
      <v-row>
        <v-col class="col-6">
          <menu-icon
              :color="iconColor1"
              :iconTitle="iconTitle1"
              :iconName="iconName1"></menu-icon>
        </v-col>
        <v-col class="col-6">
          <menu-icon
              :iconTitle="iconTitle2"
              :iconName="iconName2"></menu-icon>
        </v-col>
      </v-row>
  </div>
</template>

<script>

import MenuIcon from "./MenuIcon";

export default {
  name: 'Footer',
  components: { MenuIcon },
  data: ()=>{
      return {
        iconColor1: "#D8E2FF",
        iconTitle1: "最適スケジュール",
        iconTitle2: "マップ",
        iconName1: "format_list_bulleted",
        iconName2: "near_me"
      }
    }
}
</script>

<style scoped>
#footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  text-align: center;
  background-color: #364057;
  padding-top: 1%;
  padding-bottom: 3%;
  margin-left: -3%;
}
</style>

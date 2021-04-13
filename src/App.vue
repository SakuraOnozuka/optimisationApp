<template>

  <div id="app">
    <div id="header">
      <div class="mt-10" id="title">最適スケジュール</div>
      <v-icon dark id="icon">
        settings
      </v-icon>
    </div>

    <v-container>
      <v-row dense>
        <v-col cols="12">
          <div>現在の作業</div>
          <Schedule
          :name="name1"
          :ratio="ratio1"
          :message="message1"
          :number="number1"
          :count="count1"
          :time="time1"
          :title="title1"
          :show="true"
          :color="color1"
          ></Schedule>
          <br>
          <v-row>
            <v-col
                cols="6"
                style="padding-bottom: 0;
                       padding-top: 2.5%;
                       vertical-align: text-bottom;">
              <div>次の作業</div>
            </v-col>
            <v-col
                class="col-6"
                style="padding-bottom: 0;
                       padding-top: 0;
                       float: right;">
              <v-btn
                depressed
                rounded
                style="color: #AEB9D6;
                       background-color: #4B5771;
                       border-color: #4B5771;
                       padding-right: 0;
                       float: right;
                       right: 5%">
                <v-icon dark small>format_list_bulleted</v-icon>
                <div style="font-size: 1rem">一覧を表示</div>
              </v-btn>
            </v-col>
          </v-row>
          <Schedule
              :name="name2"
              :ratio="ratio2"
              :message="message2"
              :number="number2"
              :count="count2"
              :time="time2"
              :title="title2"
              :color="color2"
          ></Schedule>
        </v-col>
      </v-row>
      <v-row>
        <Footer></Footer>
      </v-row>
    </v-container>
</div>

</template>

<script>
import Schedule from './components/Schedule.vue'
import Footer from "./components/Footer";

export default {
  name: 'App',
  components: {
    Schedule,
    Footer
  },
  data: ()=>{
    return {
      name1:"1B　ABCD123",
      name2: "1C　EFGH123",
      message1: "10:09",
      message2: "11:49",
      time1: "18:59:59",
      time2: "19:01:39",
      title1: "加工基準ノック穴下穴開け",
      title2: "オイルパン組付けノック穴仕上げ",
      color1: "#E7B81D",
      color2: "#00CB37",
      ratio1: 75,
      ratio2: 0,
      number1: 2,
      number2: 3,
      count1: 30,
      count2: 30
      }
    }
}
</script>

<style scoped>
#app {
  background-color: #4B5771;
  color: #FFFFFF;
  padding-top: 2%;
  padding-right: 3%;
  padding-left: 3%;
  height: 100vh;
  font-family: "ＭＳ Ｐゴシック";
  font-size: 1.1rem;
}
#title {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding-top: 1%;
  text-align: center;
  margin-top: 4%;
  margin-bottom: 5%;
}
#header {
  position: relative;
}
#icon {
  float: right;
  position: absolute;
  top: 0;
  right: 5%;
}
</style>

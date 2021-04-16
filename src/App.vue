<template>
  <div id="back">
    <div id="body">
      <div id="header">
        <div class="mt-10" id="title">最適スケジュール</div>
        <v-btn icon id="setting-icon" dark>
          <v-icon>
            settings
          </v-icon>
        </v-btn>
      </div>
      <v-container>
        <v-row dense>
          <v-col cols="12">
            <div>現在の作業</div>
            <TaskCard
            :name="name1"
            :ratio="ratio1"
            :message="message1"
            :number="number1"
            :count="count1"
            :time="time1"
            :title="title1"
            :show="true"
            :color="color1"
            ></TaskCard>
            <br>
            <v-row>
              <v-col
                  cols="6"
                  class="next-task"
              >
                <div>次の作業</div>
              </v-col>
              <v-col class="col-6 btn-for-list">
                <v-btn
                  depressed
                  rounded
                  style="color: #AEB9D6;
                         background-color: #4B5771;
                         border-color: #4B5771;
                         padding-left: 0;
                         padding-right: 0;
                         float: right;
                         right: 5%">
                  <v-icon dark small>format_list_bulleted</v-icon>
                  <div style="font-size: 3vw;">一覧を表示</div>
                </v-btn>
              </v-col>
            </v-row>
            <TaskCard
                :name="name2"
                :ratio="ratio2"
                :message="message2"
                :number="number2"
                :count="count2"
                :time="time2"
                :title="title2"
                :color="color2"
            ></TaskCard>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <v-footer id="footer">
      <Footer></Footer>
    </v-footer>
  </div>
</template>

<script>
import TaskCard from './components/TaskCard.vue'
import Footer from "./components/Footer";

export default {
  name: 'App',
  components: {
    TaskCard,
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
  #back{
    background-color: #4B5771;
    color: #FFFFFF;
    height: 100vh;
  }
  #body {
    padding-top: 2%;
    padding-right: 3%;
    padding-left: 3%;
    margin-left: 0;
    font-family: "ＭＳ Ｐゴシック";
    font-size: 3.5vw;
    transform: rotate(0.1deg);
  }
  #title {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    padding-top: 2%;
    text-align: center;
    margin-top: 3%;
    margin-bottom: 7%;
    font-size: 4vw;
  }
  #header {
    position: relative;
  }
  #setting-icon {
    float: right;
    position: absolute;
    top: 0;
    right: 5%;
  }
  #footer {
    margin-left: -3%;
    width: content-box;
    padding-top: 0;
    padding-bottom: 0;
  }
  .next-task {
    padding-bottom: 0;
    padding-top: 2.5%;
    vertical-align: text-bottom;
  }
  .btn-for-list {
    padding-bottom: 0;
    padding-top: 0;
    float: right;
  }
</style>

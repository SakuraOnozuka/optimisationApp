<template>
  <div>
      <v-card
          class="mx-auto"
          outlined
          style="background-color: #ECF0F7;
                 padding: 2% 2% 4% 2%;
                 margin: 4% 0%;
                 border-radius: 3%"
      >
        <v-card-text style="padding-bottom: 0">
          <v-row
            style="font-size: 1rem;
                   font-weight: 900;
                   color:black;"
            class="font"
          >{{title}}</v-row>
          <v-row>
            <v-icon
                x-small
                v-bind:style="{ color: color }"
                >circle</v-icon>
            <div
              style="color: black;
                     font-size: 0.9rem;
                     font-family: Tahoma;
                     font-weight: 500">
              {{name}}
            </div>
          </v-row>
        <v-row>
          <v-col class="col-5">
            <v-progress-circular
                :rotate="-90"
                :width="width"
                :value="ratio"
                color="#7C7BFF"
                :size="size"
            >
              <div class="font-for-number">{{ message }}</div>
            </v-progress-circular>
          </v-col>

          <v-col
              class="col-7"
          >
            <v-row
                style="padding-right: 12%;
                       margin-top: auto;
                       margin-bottom: auto;">
              <v-col
                  class="col-7"
                  style="font-size: 0.94rem;
                         font-family: ＭＳ Ｐゴシック;
                         font-weight: 100;
                         line-height: 1.8;
                         color: #A3B0C7;">
                歯具連番 <br>
                残カウント <br>
                交換時刻
              </v-col>
          <v-col
              class="col-5 font-for-number"
              style="color: black;
                     padding-left: 0;
                     font-size: 1rem;
                     line-height: 1.7;
                     font-weight: 500;">
            {{number}}<br>
            {{count}}<br>
            {{time}}
          </v-col>
        </v-row>
          </v-col>
        </v-row>
          </v-card-text>
      <div v-show="show">
        <v-card-actions>
          <v-btn
              outlined
              style="width: 100%;
                     background-color: #7B7CFE;
                     color: #FFFFFF;
                     height: 3rem;"
          >
            <v-icon
                style="font-weight: 900;
                          font-size: 1.1rem;"
                dark>done</v-icon>
              <div style="font-weight: 900;
                          font-size: 1.1rem;"
              >作業を完了</div>
          </v-btn>
        </v-card-actions>
      </div>
      </v-card>
  </div>
</template>

<script>
  export default {
    name: 'Schedule',
    props: {
      name: {
        type: String,
        required: true,
        default: "1B ABCS123"
      },
      color: {
        type: String,
        required: true,
        default: "#E7B81D"
      },
      ratio: {
        type: Number,
        required: true,
        default: 10
      },
      message: {
        type: String,
        required: true,
        default: "10"
      },
      number: {
        type: Number,
        required: true,
        default: 10
      },
      count: {
        type: Number,
        required: true,
        default: 10
      },
      time: {
        type: String,
        required: true,
        default: "18:59:59"
      },
      title: {
        type: String,
        required: true,
        default: "10:09"
      },
      show: {
        type: Boolean,
        required: false,
        default: false
      }
    },
    computed:{
      size: function (){
        return document.body.clientWidth/4.5;
      },
      width: function (){
        return document.body.clientWidth/80;
      }
    }
  }
</script>
<style scoped>
.font-for-number {
  color: black;
  font-family: arial;
  font-weight: 500;
  font-size:1.5rem
}
.font {
  font-family: "ＭＳ Ｐゴシック"
}
</style>

<template>
  <div>
    <v-card
        class="mx-auto card"
        outlined>
      <v-card-text class="card-text">
        <v-row class="font title">{{title}}</v-row>
        <v-row>
          <v-icon
              x-small
              v-bind:style="{ color: color }"
              >circle</v-icon>
          <div class="name">{{name}}</div>
        </v-row>
      <v-row class="padding">
        <v-col class="col-4 center">
          <div style="padding-bottom: 4%">
          <v-progress-circular
              :rotate="-90"
              :width="width"
              :value="ratio"
              color="#7C7BFF"
              :size="size">
            <div class="font-for-number">{{ message }}</div>
          </v-progress-circular>
          </div>
        </v-col>
        <v-col cols="1"></v-col>
        <v-col class="col-7 center">
          <v-row class="list">
            <v-col
                cols="6"
                class="list-title">
              歯具連番<br>
              残カウント<br>
              交換時刻
            </v-col>
        <v-col class="col-5 font-for-number list-figure">
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
                   height: 3rem;">
          <v-icon class="btn-icon" dark>done</v-icon>
            <div class="btn-title">作業を完了</div>
        </v-btn>
      </v-card-actions>
    </div>
    </v-card>
  </div>
</template>

<script>
export default {
  name: 'TaskCard',
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
      return document.body.clientWidth/4.3;
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
    font-size: 6vw;
  }
  .font {
    font-family: "ＭＳ Ｐゴシック"
  }
  .padding {
    padding-bottom: 3%;
    padding-top: 3%;
  }
  .center {
    top:  0;
    bottom:  0;
    left:  0;
    right:  0;
    margin:  auto;
  }
  .card {
    background-color: #ECF0F7;
    padding: 2% 2% 4% 2%;
    margin: 4% 0%;
    border-radius: 3%
  }
  .card-text {
    padding-bottom: 0;
    padding-left: 7%;
    padding-right: 0;
    line-height: 1.5
  }
  .title {
    font-size: 3.2vw;
    font-weight: 900;
    color:black;
  }
  .name {
    color: black;
    font-size: 3.2vw;
    font-family: Tahoma;
    font-weight: 500
  }
  .list {
    margin-top: auto;
    margin-bottom: auto;
  }
  .list-title {
    font-size: 3vw;
    transform: rotate(0.1deg);
    font-family: ＭＳ Ｐゴシック;
    font-weight: 100;
    line-height: 1.87;
    color: #A3B0C7;
  }
  .list-figure {
    color: black;
    padding-left: 0;
    font-size: 3vw;
    line-height: 1.87;
    font-weight: 500;
  }
  .btn-icon {
    font-weight: 900;
    font-size: 3vw;
  }
  .btn-title {
    font-weight: 900;
    font-size: 3vw;
  }
</style>

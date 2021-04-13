<template>
  <div>
      <v-card
          class="mx-auto"
          outlined
          style="background-color: #ECF0F7;
                 padding: 3%;
                 margin: 4% 0%;
                 border-radius: 3%"
      >
        <v-card-text>
          <v-row
            style="font-size: 1rem;
                   font-weight: bold;
                   color:black;">{{title}}</v-row>
          <v-row>
            <v-icon
                x-small
                v-bind:style="{ color: color }"
                >circle</v-icon>
            <div
              style="color: black;
                      font-size: 1rem">
              {{name}}
            </div>
          </v-row>
        <v-row>
          <v-col class="col-5">
            <v-progress-circular
                :rotate="-90"
                :size="size()"
                :width="width()"
                :value="ratio"
                color="#96AAEF"
            >
              <div style="color: black;
                          font-weight: 500;
                          font-size:1.3rem">{{ message }}</div>
            </v-progress-circular>
          </v-col>

          <v-col
              class="col-7"
          >
            <v-row>
              <v-col
                  class="col-7"
                  style="font-size: 1rem;
                         font-weight: 200;
                         color: #A3B0C7">
                歯具連番 <br>
                残カウント <br>
                交換時刻
              </v-col>
          <v-col
              class="col-5"
              style="color: black;
                     padding-left: 0;
                     font-size: 1rem;
                     font-weight: 550">
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
            <v-icon dark>done</v-icon>
              <div style="font-weight: bolder;
                          font-size: 1rem;"
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
    methods:{
      size(){
        return window.innerWidth/4;
      },
      width(){
        return window.innerWidth/80;
      }
    }
  }
</script>
<style scoped>

</style>

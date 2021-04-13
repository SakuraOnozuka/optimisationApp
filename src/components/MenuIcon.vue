<template>
  <div>
    <v-btn icon>
      <v-icon :style="{ color: color }">
        {{iconName}}
      </v-icon>
    </v-btn>
    <div
        style="text-align:center;
               transform: rotate(0.1deg);
               font-size: 0.7rem;"
        :style="{ color: color }">{{iconTitle}}</div>
   </div>
</template>

<script>

export default {
  name: 'MenuIcon',
  props: {
    iconName: {
      type: String,
      required: true,
      default: "format_list_bulleted"
    },
    color: {
      type: String,
      required: false,
      default: "#6B78A0"
    },
    iconTitle: {
      type: String,
      required: true,
      default: "最適スケジュール"
    },
  }
}
</script>

<style scoped>
</style>

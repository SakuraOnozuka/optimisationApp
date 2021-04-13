<template>
  <div>
    <v-btn icon>
      <v-icon :style="{ color: color }">
        {{iconName}}
      </v-icon>
    </v-btn>
    <div
        style="text-align:center;
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
      required: true,
      default: "#D8E2FF"
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

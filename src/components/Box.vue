<template>  
  <div>
    <v-card class="box" v-for="(box, i) in params" :key="i">
      <Box v-if="box.children.length > 0" :params="box.children" />
      <v-card-text v-else>{{box.params.number}}</v-card-text>
    </v-card>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export interface BoxParams {
  params: object;
  children: BoxParams[];
}

const Box = Vue.extend({
  name: 'Box',
  props: {
    params: {
      type: Array,
      default: [],
      required: true,
    },
  },
  data: () => ({}),
});

export default Box;
</script>

<style lang="scss" scoped>
.box {
  margin: 4px;
}
</style>

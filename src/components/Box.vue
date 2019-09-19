<template>
  <v-card class="box">
    <v-card-text>
      <Box v-if="Array.isArray(parameters)" parameters="parameters" />
      <span v-else><slot /></span>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: {
    parameters: Number,
  },
  data: () => ({}),
});
</script>

<style lang="scss" scoped>
.box {
  margin: 4px;
}
</style>

<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span class="font-weight-light">Flexbox Playground</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn 
        text
        @click.stop="drawer = !drawer">        
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-content>
      <v-navigation-drawer 
        v-model="drawer"
        absolute temporary right>
        <template v-slot:prepend>
          
        </template>
      </v-navigation-drawer>

      <v-container fluid class="d-flex">
        <div v-for="(box, i) in boxes" :key="i">
          <Box parameters={box}>{{i}}</Box>
        </div>
      </v-container>

    </v-content>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import Box from './components/Box.vue';

export default Vue.extend({
  name: 'App',
  components: {
    Box,
  },
  data: () => ({
    drawer: false,
    boxes: [1, 2, 3, [4, 5, 6]],
  }),
});
</script>

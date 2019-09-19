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
        <Box :params="boxes" />
      </v-container>

    </v-content>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import Box, { BoxParams } from './components/Box.vue';

const initial: BoxParams[] = [
  {
    params: {
      flex: true,
      number: '1',
    },
    children: [
      {
        params: {
          flex: false,
          number: '1-1',
        },
        children: [],
      },
      {
        params: {
          flex: true,
          number: '1-2',
        },
        children: [],
      },
    ],
  },
  {
    params: {
     flex: false,
     number: '2',
    },
    children: [],
  },
];

export default Vue.extend({
  name: 'App',
  components: {
    Box,
  },
  data: () => ({
    drawer: false,
    boxes: initial,
  }),
});
</script>

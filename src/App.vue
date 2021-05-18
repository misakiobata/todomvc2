<template>
  <v-app>
  <v-container>
    <router-link to="/">all</router-link> |
    <router-link to="/about">done</router-link>

    <router-view/>
  </v-container>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';


export default Vue.extend({
  name: 'App',

  data: () => ({

  }),
  computed:{

  }
});
</script>

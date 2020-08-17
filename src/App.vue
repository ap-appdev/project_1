<template>
  <v-app>
    <v-main class="bg-grey">
      <Dashboard/>
    </v-main>
  </v-app>
</template>

<script>
import Dashboard from './components/Dashboard';

export default {
  name: 'App',

  components: {
    Dashboard,
  },

  data: () => ({
    //
  }),
};
</script>
<style scoped>
  .bg-grey {
    background-color: #edf2f5;
  }
</style>

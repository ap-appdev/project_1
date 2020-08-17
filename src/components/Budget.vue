<template>
  <v-container class="white pa-3 my-7">
    <v-col>
      <h2 class="d-inline">
        Бюджет
      </h2>
    </v-col>
    <v-col>
      <div class="percent-line" style="background-color: #FF5958; height: 35px;">
        <div style="background-color: #F4D1CF; width: 25%;"></div>
      </div>
    </v-col>
    <v-simple-table style="width: 100%">
      <template v-slot:default>
        <thead>
        <tr>
          <th class="text-button text-left">Бюджет</th>
          <th class="text-button text-left">Потрачено</th>
          <th class="text-button text-left">Осталось</th>
          <th class="text-button text-left">Перерасход</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="item in budget" :key="item.name">
          <td>{{ item.name }}</td>
          <td>{{ item.calories }}</td>
        </tr>
        </tbody>
      </template>
    </v-simple-table>
  </v-container>
</template>

<script>

  export default {
    name: 'Budget',
    props: '',
    components: {
    },
    data: () => ({
      budget: []
    }),
    mounted () {
    }
  }
</script>

<style scoped>
  .percent-line {
    position: relative;
    border-radius: 5px;
    width: 100%;
  }

  .percent-line > div:first-child {
    position: absolute;
    height: 100%;
    border-top-right-radius: 5px;
    border-bottom-right-radius: 5px;
    top: 0;
    right: 0;
  }
</style>

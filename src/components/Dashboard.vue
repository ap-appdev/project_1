<template>
  <div>
    <v-container class="pb-0">
      <v-row align="center">
        <v-col class="d-flex flex-row" cols="12" sm="6">
          <v-select
                  :items="periods"
                  label="Период"
                  hide-details
                  class="pa-0 my-0 mr-2"
          ></v-select>
          <v-select
                  :items="filials"
                  label="Филиал"
                  hide-details
                  class="pa-0 my-0 mr-2"
          ></v-select>
          <v-select
                  :items="regions"
                  label="Регион"
                  hide-details
                  class="pa-0 my-0 mr-2"
          ></v-select>
          <v-select
                  :items="lawyers"
                  label="Юрист"
                  hide-details
                  class="pa-0 my-0 mr-2"
          ></v-select>
        </v-col>
        <v-col class="text-right" cols="12" sm="6">
          <span class="text--disabled">Сохранить отчет</span>
          <v-btn text color="primary">XLS</v-btn>
          <v-btn text color="primary">CSV</v-btn>
          <v-btn text color="primary">PDF</v-btn>
        </v-col>
      </v-row>
    </v-container>
    <expenses></expenses>
    <budget></budget>
  </div>
</template>

<script>
  import Expenses from './Expenses';
  import Budget from './Budget';

  export default {
    name: 'Dashboard',
    components: {
      Expenses,
      Budget
    },
    data: () => ({
      periods: [
              '2014'
      ],
      filials: [
              'Все'
      ],
      regions: [
              'Все'
      ],
      lawyers: [
              'Все'
      ]
    }),
    mounted () {
    }
  }
</script>

<style scoped>
</style>

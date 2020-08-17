<template>
  <v-container class="white pa-3 my-7">
    <v-col>
      <h2 class="d-inline">
        Расходы
      </h2>
      <v-btn text small color="primary" class="mx-2">Квартал</v-btn>
      <v-btn text small color="primary" class="active">Месяц</v-btn>
    </v-col>
    <bars-diagram
            v-if="!loaded"
            :chartdata="chartdata"
            :options="options"
            style="width: 100%"
            :height="550"
    ></bars-diagram>
    <v-simple-table style="width: 100%">
      <template v-slot:default>
        <thead>
        <tr>
          <th class="text-button text-left">Расходы</th>
          <th class="text-button text-right">Сумма по искам</th>
          <th class="text-button text-center">Исков</th>
          <th class="text-button text-right">Снижение требований</th>
          <th class="text-button text-right">Итоговая сумма</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="item in expenses" :key="item.name">
          <td>{{ item.name }}</td>
          <td>{{ item.calories }}</td>
        </tr>
        </tbody>
      </template>
    </v-simple-table>
  </v-container>
</template>

<script>
  import BarsDiagram from './charts/BarsDiagram';

  export default {
    name: 'Expenses',
    props: '',
    components: {
      BarsDiagram,
    },
    data: () => ({
      loaded: true,
      chartdata: null,
      options: null,
      selected: [],
      expenses: [],
    }),
    mounted () {
      this.loaded = true
      this.chartdata = {
        labels: ['', 'АПР', '', 'МАЙ', '', 'ИЮН', '', 'ИЮЛ', '', 'АВГ', '', 'СЕНТ', '', 'ОКТ', '', 'НОЯ', '', 'ДЕК'],
        datasets: [{
          label: 'Dataset 1',
          backgroundColor: "red",
          data: [
            1,
            2,
            1,
            1,
            1,
            1,
            1,
            1,
            2,
            1,
            1,
            1,
            1,
            1,
            5,
            7,
            5,
            7
          ]
        }, {
          label: 'Dataset 2',
          backgroundColor: "blue",
          data: [
            1,
            1,
            1,
            1,
            1,
            1,
            1,
            1,
            2,
            1,
            1,
            1,
            1,
            1,
            5,
            7,
            5,
            7
          ]
        }, {
          label: 'Dataset 3',
          backgroundColor: "green",
          data: [
            1,
            1,
            1,
            1,
            1,
            4,
            1,
            1,
            2,
            1,
            1,
            1,
            1,
            1,
            5,
            7,
            5,
            7
          ]
        }]
      }
      this.options = {
        events: [],
        legend: "",
        title: {
          position: "left",
          display: true,
          text: 'млн. рублей'
        },
        tooltips: {
          mode: 'index',
          intersect: false
        },
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          xAxes: [{
            stacked: true,
          }],
          yAxes: [{
            stacked: true
          }]
        }
      }
      this.loaded = false
    }
  }
</script>

<style scoped>
  .active {
    background-color: rgb(210,228,233);
  }
  .v-data-table tr:hover:not(.v-data-table__expanded__content) {
    background: #fff
  }
</style>

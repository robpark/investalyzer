<template>
  <v-container>
    <h1>Investments</h1>
    <v-row>
      <v-col cols="8">
        <v-data-table
          :headers="headers"
          :items="positions"
          :items-per-page="10"
          class="elevation-1"
        >
        </v-data-table>
      </v-col>
      <v-col cols="4">
        <InvestmentStatistics />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import positionData from '../data/positions.json';
import InvestmentStatistics from '../components/InvestmentStatistics';

export default {
  components: { InvestmentStatistics },
  data() {
    return {
      headers: [
        { text: 'Symbol', align: 'start', value: 'symbol' },
        { text: 'Type', value: 'security-type' },
        { text: 'Price', align: 'right', value: 'price' },
        { text: 'Quantity', align: 'right', value: 'quantity' }
      ],
      positions: positionData
    };
  }
};
</script>

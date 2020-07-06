<template>
  <div>
    <h1>Investments</h1>
    <v-data-table :headers="headers" :items="positions" :items-per-page="10" class="elevation-1">
    </v-data-table>
  </div>
</template>

<script>
import positionData from '../data/positions.json';

export default {
  data() {
    return {
      headers: [
        {
          text: 'Symbol',
          align: 'start',
          value: 'symbol'
        },
        { text: 'Type', value: 'security-type' },
        { text: 'Price', value: 'price' },
        { text: 'Quantity', value: 'quantity' }
      ],
      positions: positionData
    };
  }
};
</script>

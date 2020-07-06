<template>
  <div>
    <v-card class="d-flex align-content-start flex-wrap" flat tile min-height="200">
      <v-card
        v-for="percent in percents"
        :key="`${percent.type}`"
        width="160"
        class="pa-2"
        outlined
        tile
      >
        <v-card-title>{{ percent.type }}</v-card-title>
        <v-card-text>{{ percent.percent }}</v-card-text>
      </v-card>
    </v-card>
  </div>
</template>

<script>
import positionData from '../data/positions.json';

export default {
  name: 'InvestmentStatistics',
  data() {
    return {
      positions: positionData
    };
  },
  computed: {
    percents: {
      get() {
        let total = 0;
        let totalsByType = {
          cash: 0,
          stock: 0
        };
        this.positions.forEach(position => {
          console.log(position);
          total += position.price * position.quantity;
          if (position['security-type'] === 'Cash') {
            totalsByType.cash += position.price * position.quantity;
          } else if (position['security-type'] === 'Stock') {
            totalsByType.stock += position.price * position.quantity;
          }
        });
        return [
          { type: 'Stock', percent: `${Math.round((totalsByType.stock / total) * 100)} %` },
          { type: 'Cash', percent: `${Math.round((totalsByType.cash / total) * 100)} %` },
          { type: 'Total Stock', percent: `$ ${totalsByType.stock}` },
          { type: 'Total Cash', percent: `$ ${totalsByType.cash}` },
          { type: 'Total', percent: `$ ${total}` }
        ];
      }
    }
  }
};
</script>

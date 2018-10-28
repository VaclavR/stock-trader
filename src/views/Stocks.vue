<template>
  <div class="stocks">
    <h1>This is a stocks page</h1>
    <div class="row">
      <StocksStock v-for="stock in stocks" :key="stock.id" :stock="stock"/>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import StocksStock from '@/components/StocksStock.vue'; // @ is an alias to /src

@Component({
  components: {
    StocksStock,
  },
})
export default class Stocks extends Vue {
  public stocks = [
    { id: 1, name: 'BMW', price: 110 },
    { id: 2, name: 'Tesla', price: 190 },
    { id: 3, name: 'Mercedes', price: 120 },
    { id: 4, name: 'Google', price: 220 },
  ];
}
</script>

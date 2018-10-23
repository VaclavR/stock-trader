<template>
  <div class="stocks">
    <h1>This is a stocks page</h1>
    <StocksStock/>
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
export default class Stocks extends Vue {}
</script>

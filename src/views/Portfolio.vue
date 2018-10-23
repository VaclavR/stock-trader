<template>
  <div class="portfolio">
    <h1>This is a portfolio page</h1>
    <PortfolioStock/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import PortfolioStock from '@/components/PortfolioStock.vue'; // @ is an alias to /src

@Component({
  components: {
    PortfolioStock,
  },
})
export default class Portfolio extends Vue {}
</script>
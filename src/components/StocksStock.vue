<template>
    <div class="col-sm-6 col-md-4 mt-3">
        <div class="card">
            <div class="card-body">
                <div class="card-title clearfix">
                    <h3 class="float-left">{{ stock.name }}</h3>
                    <span class="small float-right">(Price: {{ stock.price }})</span>
                </div>
                <div class="float-left">
                    <input type="number" class="form-control" placeholder="Quantity" v-model="quantity">
                </div>
                <div class="float-right">
                    <button class="btn btn-success" @click="buyStock" :disabled="quantity <= 0">Buy</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class StocksStock extends Vue {
     @Prop() private stock: any;
     private quantity = 0;

     private buyStock() {
         const order = {
             stockId: this.stock.id,
             stockPrice: this.stock.price,
             quantity: this.quantity,
         }
         console.log(order);
         this.quantity = 0;
     }
}
</script>
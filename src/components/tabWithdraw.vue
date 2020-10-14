<template>
  <v-row>
    <v-col cols="6" offset="3">
      <v-row>
        <v-col cols="12" class="pa-0">
          <v-select
              :items="exchanges"
              flat
              background-color="border"
              color="dark"
              solo
              v-model="exchange"
              placeholder="Choose exchange"
          >
          </v-select>
        </v-col>
        <v-col cols="12" class="pa-0">
          <v-select :items="currencies"
                    flat
                    background-color="border"
                    solo v-model="currency"
                    placeholder="Choose currency"
          >
          </v-select>
        </v-col>
        <v-col cols="12" class="pa-0">
          <v-text-field v-model="amount"
                        flat
                        background-color="border"
                        solo
                        placeholder="Withdraw amount">
            <template v-slot:append>
              <v-btn color="label" elevation="0" dark>Max</v-btn>
            </template>
          </v-text-field>
        </v-col>
        <v-col cols="12" class="pt-7 pl-0 pr-0 pb-7">
          <v-btn block color="primary" large>Rebalance</v-btn>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'tabWithdraw',
  data () {
    return {
      amount: null,
      exchanges: ['Kraken', 'SwapZilla', 'Binance'],
      exchange: null,
      currencies: ['BTC', 'ETH', 'XMR'],
      currency: null
    }
  }
}
</script>

<style scoped>

</style>

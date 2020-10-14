<template>
  <v-row>
    <v-col cols="6" offset="3">
      <v-row>
        <v-col cols="12" class="pa-0">
          <v-select :items="exchanges" flat background-color="border" color="dark" solo v-model="exchange" placeholder="Choose exchange"></v-select>
        </v-col>
        <v-col cols="12" class="pa-0">
          <v-select :items="currencies" flat background-color="border" solo v-model="currency" placeholder="Choose currency">
            <template></template>
          </v-select>
        </v-col>
        <v-col cols="12" class="pa-0">
          <div class="d-flex justify-center mb-6">
            <v-img src="@/assets/qr.png" max-width="120" max-height="120" />
          </div>
        </v-col>
        <v-col cols="12" class="pa-0 text-center">
          FGBfvcnkfdnvkk74365832ybvcvdfvfvb
        </v-col>
        <v-col cols="12" class="pt-7 pl-0 pr-0 pb-7">
          <v-btn block large color="primary">Copy</v-btn>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'tabDeposit',
  data () {
    return {
      exchanges: ['Kraken', 'SwapZilla', 'Binance'],
      exchange: 'Kraken',
      currencies: ['BTC', 'ETH', 'XMR'],
      currency: null
    }
  }
}
</script>

<style scoped>

</style>

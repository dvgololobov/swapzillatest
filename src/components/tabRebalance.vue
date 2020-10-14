<template>
  <v-row>
    <v-col cols="6" offset="3">
      <v-row>
        <v-col cols="12" class="pa-0 pt-2 pb-1">
          From
        </v-col>
        <v-col cols="12" class="pa-0 pt-2 pb-1">
          <v-select
              :items="exchanges"
              flat
              background-color="border"
              color="dark"
              solo
              label="From"
              v-model="exchange"
              placeholder="Choose exchange"
          >
          </v-select>
        </v-col>
        <v-col cols="12" class="pa-0">
          To
        </v-col>
        <v-col cols="12" class="pa-0">
          <v-select
              :items="exchanges"
              flat
              background-color="border"
              color="dark"
              solo
              label="From"
              v-model="exchangeTo"
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
          <v-autocomplete v-model="amount" flat solo background-color="border" placeholder="Amount">
            <template v-slot:no-data>
              <v-row class="ma-0" style="max-width: 360px;">
                <v-col cols="12">
                  <v-chip text-color="primary" label class="balanceChip">
                    Balance:&nbsp;<strong>0.04763864</strong>
                  </v-chip>
                </v-col>
                <v-col cols="12">
                  <div class="d-flex justify-start">
                    <v-btn color="label" class="ma-1" small dark>10%</v-btn>
                    <v-btn color="label" class="ma-1" small dark>25%</v-btn>
                    <v-btn color="label" class="ma-1" small dark>50%</v-btn>
                    <v-btn color="label" class="ma-1" small dark>100%</v-btn>
                    <v-btn color="label" class="ma-1" small dark>Split</v-btn>
                  </div>
                </v-col>
              </v-row>
            </template>
          </v-autocomplete>
        </v-col>
        <v-col cols="12" class="pt-7 pl-0 pr-0 pb-7">
          <v-btn block color="primary" large>Withdraw</v-btn>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'tabRebalance',
  data () {
    return {
      amount: null,
      exchanges: ['Kraken', 'SwapZilla', 'Binance'],
      exchange: null,
      exchangeTo: null,
      currencies: ['BTC', 'ETH', 'XMR'],
      currency: null
    }
  }
}
</script>

<style scoped lang="scss">
.balanceChip {
  font-size: 0.75rem;
  background-color: rgba(42, 101, 145, 0.1) !important;
}
</style>

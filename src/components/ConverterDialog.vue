<template>
  <div>
    <v-row>
      <v-col cols="12">
        <v-dialog v-model="showDialog" max-width="780" transition="dialog-bottom-transition">
          <template v-slot:activator="{ on, attrs }">
            <v-btn v-bind="attrs" v-on="on">
              Show dialog
            </v-btn>
          </template>
          <v-card>
            <v-toolbar light elevation="0">
              <v-tabs v-model="tab" color="dark" class="pa-4">
                <v-tabs-slider color="dark"></v-tabs-slider>
                <v-tab v-for="item in tabs" :key="item.code">
                  {{ item.text }}
                </v-tab>
              </v-tabs>
              <v-spacer></v-spacer>
              <v-btn color="label" icon @click="showDialog = false">
                <v-icon>mdi-close</v-icon>
              </v-btn>
            </v-toolbar>
            <v-card-text class="pa-10">
              <v-tabs-items v-model="tab">
                <v-tab-item v-for="item in tabs" :key="item.code">
                  <component :is="item.component" />
                </v-tab-item>
              </v-tabs-items>
            </v-card-text>
          </v-card>
        </v-dialog>
      </v-col>
    </v-row>
  </div>
</template>

<script>

import TabDeposit from '@/components/tabDeposit'
import TabWidthdraw from '@/components/tabWithdraw'
import TabRebalance from '@/components/tabRebalance'
export default {
  name: 'ConverterDialog',
  components: { TabRebalance, TabDeposit, TabWidthdraw },
  data () {
    return {
      notifications: false,
      tab: 0,
      tabs: [
        {
          code: 'deposit',
          text: 'Deposit',
          component: 'TabDeposit'
        },
        {
          code: 'withdraw',
          text: 'Withdraw',
          component: 'TabWidthdraw'
        },
        {
          code: 'rebalance',
          text: 'Rebalance',
          component: 'TabRebalance'
        }
      ],
      showDialog: false
    }
  }
}
</script>

<style scoped lang="scss">
.qrCodeImage {
  width: 120px;
  height: 120px;
}
</style>

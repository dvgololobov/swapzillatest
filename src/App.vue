<template>
  <v-app class="basicStyles">
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        Test modal dialog for Swapzilla
      </div>
    </v-app-bar>
    <v-main>
      <v-container>
        <router-view />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data: () => ({
    dataValue: 0
  })
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,600;1,300;1,600&display=swap');
.basicStyles {
  font-family: 'Open Sans', sans-serif;
}
.v-btn__content {
  text-transform: none;
}
.v-tab {
  font-family: 'Open Sans', sans-serif;
  text-transform: none !important;
  font-size: 1.25rem !important;
  line-height: 1.55rem !important;
}
.v-tab--active {}
</style>

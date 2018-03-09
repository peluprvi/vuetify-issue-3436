<template>
  <v-app dark>
    <v-content>
      <v-container fluid>
        <v-slide-y-transition mode="out-in">
          <router-view></router-view>
        </v-slide-y-transition>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  import Meta from 'mixins/meta'

  export default {
    mixins: [Meta]
  }
</script>

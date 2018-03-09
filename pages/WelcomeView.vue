<template>
  <v-content>
    <v-container fluid grid-list-lg>
      <v-layout>
        <v-flex>
          <ol>
            <li>Open me at window width >= 960px</li>
            <li>Hit F5</li>
            <li>Expand the window width (1px or more)</li>
          </ol>
        </v-flex>
      </v-layout>
      <v-layout>
        <v-flex>
          <v-card color="accent" v-if="$vuetify.breakpoint.smAndDown">
            <v-card-title>I'm displayed at $vuetify.breakpoint.smAndDown</v-card-title>
          </v-card>
          <v-card color="primary" v-else>
            <v-card-title>I'm displayed at !$vuetify.breakpoint.smAndDown</v-card-title>
          </v-card>
        </v-flex>
        <v-flex>
          <v-card color="accent" v-if="isSmAndDownComputed">
            <v-card-title>I'm displayed at isSmAndDownComputed</v-card-title>
          </v-card>
          <v-card color="primary" v-else>
            <v-card-title>I'm displayed at !isSmAndDownComputed</v-card-title>
          </v-card>
        </v-flex>
        <!-- VVV for some reason it works if you remove this commented area VVV -->
        <!-- but, of course isSmAndDownMounted will not update when you change the window width -->
        <!--
        <v-flex>
          <v-card color="accent" v-if="isSmAndDownMounted">
            <v-card-title>I'm displayed at isSmAndDownMounted</v-card-title>
          </v-card>
          <v-card color="primary" v-else>
            <v-card-title>I'm displayed at !isSmAndDownMounted</v-card-title>
          </v-card>
        </v-flex>
        -->
        <!-- ^^^ for some reason it works if you remove this commented area ^^^ -->
      </v-layout>
      <v-layout :column="$vuetify.breakpoint.smAndDown">
        <v-flex>
          :column="$vuetify.breakpoint.smAndDown"
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 1</v-card-title>
          </v-card>
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 2</v-card-title>
          </v-card>
        </v-flex>
      </v-layout>
      <v-layout :class="{[$vuetify.breakpoint.smAndDown ? 'column' : 'row']: true}">
        <v-flex>
          :class="{[$vuetify.breakpoint.smAndDown ? 'column' : 'row']: true}"
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 3</v-card-title>
          </v-card>
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 4</v-card-title>
          </v-card>
        </v-flex>
      </v-layout>
      <v-layout :column="isSmAndDownComputed">
        <v-flex>
          :column="isSmAndDownComputed"
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 5</v-card-title>
          </v-card>
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 6</v-card-title>
          </v-card>
        </v-flex>
      </v-layout>
      <v-layout :class="{[isSmAndDownComputed ? 'column' : 'row']: true}">
        <v-flex>
          :class="{[isSmAndDownComputed ? 'column' : 'row']: true}"
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 7</v-card-title>
          </v-card>
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 8</v-card-title>
          </v-card>
        </v-flex>
      </v-layout>
      <!-- VVV for some reason it works if you remove this commented area VVV -->
      <!-- but, of course isSmAndDownMounted will not update when you change the window width -->
      <!--
      <v-layout :column="isSmAndDownMounted">
        <v-flex>
          :column="isSmAndDownMounted"
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 5</v-card-title>
          </v-card>
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 6</v-card-title>
          </v-card>
        </v-flex>
      </v-layout>
      <v-layout :class="{[isSmAndDownMounted ? 'column' : 'row']: true}">
        <v-flex>
          :class="{[isSmAndDownMounted ? 'column' : 'row']: true}"
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 7</v-card-title>
          </v-card>
        </v-flex>
        <v-flex>
          <v-card>
            <v-card-title>Card 8</v-card-title>
          </v-card>
        </v-flex>
      </v-layout>
      -->
      <!-- ^^^ for some reason it works if you remove this commented area ^^^ -->
    </v-container>
  </v-content>
</template>

<script>
  export default {
    data: () => ({
      isSmAndDownMounted: undefined
    }),

    mounted () {
      this.isSmAndDownMounted = this.$vuetify.breakpoint.smAndDown
    },

    computed: {
      isSmAndDownComputed () {
        return this.$vuetify.breakpoint.smAndDown
      }
    }

  }
</script>

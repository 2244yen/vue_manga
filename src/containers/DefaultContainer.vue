<template>
  <div id="app">
    <v-app
      dark
      id="inspire"
    >
      <DefaultSidebar></DefaultSidebar>
      <v-toolbar
        color="red"
        dense
        fixed
        clipped-left
        app
      >
        <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
        <v-icon class="mx-3">fa-youtube</v-icon>
        <v-toolbar-title class="mr-5 align-center">
          <span class="title">Youtube</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-layout row align-center style="max-width: 650px">
          <v-text-field
            placeholder="Search..."
            single-line
            append-icon="search"
            :append-icon-cb="() => {}"
            color="white"
            hide-details
          ></v-text-field>
        </v-layout>
      </v-toolbar>
      <v-content>
        <v-container fill-height>
          <v-layout justify-center align-center>
            <v-flex shrink>
              <v-tooltip right>
                <v-btn
                  icon
                  large
                  :href="source"
                  target="_blank"
                  slot="activator"
                >
                  <v-icon large>code</v-icon>
                </v-btn>
                <span>Source</span>
              </v-tooltip>
            </v-flex>
          </v-layout>
        </v-container>
      </v-content>
    </v-app>
  </div>
</template>

<script>
import DefaultSidebar from './DefaultSidebar'

export default {
  components: {
    DefaultSidebar
  },
  data () {
    return {
      drawer: true
    }
  },
  props: {
    source: String
  }
}
</script>
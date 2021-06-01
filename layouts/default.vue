<template>
  <v-app>
    <nav>
      <v-toolbar dark color="orange">
        <v-toolbar-title>
          <nuxt-link to="/">Nuxtudy</nuxt-link>
        </v-toolbar-title>
        <v-spacer />
        <v-toolbar-items>
          <v-btn text nuxt to="/notice" :style="{ display: 'flex', alignItems: 'center' }">
            <div>Notice</div>
          </v-btn>
          <v-btn text nuxt to="/info" :style="{ display: 'flex', alignItems: 'center' }">
            <div>Info</div>
          </v-btn>
          <v-btn text nuxt to="/reserve" :style="{ display: 'flex', alignItems: 'center' }">
            <div>Reserve</div>
          </v-btn>
          <v-btn text nuxt to="/tip" :style="{ display: 'flex', alignItems: 'center' }">
            <div>Tip</div>
          </v-btn>
          <v-btn text nuxt to="/board" :style="{ display: 'flex', alignItems: 'center' }">
            <div>Board</div>
          </v-btn>
          <v-btn v-ripple="false" icon :style="{ display: 'flex', alignItems: 'center' }">
            <div>
              <v-icon>mdi-web</v-icon>
            </div>
          </v-btn>
        </v-toolbar-items>
      </v-toolbar>
    </nav>
    <nuxt />
  </v-app>
</template>

<script>
  export default {
    head() {
      return {
        title: 'Nuxtudy',
      };
    }
  }
</script>

<style>
</style>
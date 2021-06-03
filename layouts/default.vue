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
    <v-footer padless>
      <v-card flat tile width="100%" class="red lighten-1 text-center">
        <v-card-text>
          <v-btn class="mx-4" icon>
            <v-icon size="24px">mdi-facebook</v-icon>
          </v-btn>
          <v-btn class="mx-4" icon>
            <v-icon size="24px">mdi-twitter</v-icon>
          </v-btn>
          <v-btn class="mx-4" icon>
            <v-icon size="24px">mdi-email</v-icon>
          </v-btn>
          <v-btn class="mx-4" icon>
            <v-icon size="24px">mdi-instagram</v-icon>
          </v-btn>
          <v-btn class="mx-4" icon>
            <v-icon size="24px">mdi-phone</v-icon>
          </v-btn>
        </v-card-text>
        <v-card-text class="pt-0">
          Smooth like butter Like a criminal undercover. Gon' pop like trouble. Breakin' into your heart like that (ooh)
          Cool shade, stunner. Yeah, I owe it all to my mother. Hot like summer. Yeah, I'm makin' you sweat like that (break it down)
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          2021— <strong>Nuxtudy</strong>
        </v-card-text>
      </v-card>
    </v-footer>
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
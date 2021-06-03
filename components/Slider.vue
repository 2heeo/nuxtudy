<template>
  <div>
    <div class="slider">
      <!-- <image-slider> -->
        <transition-group name="fade" tag="div" class="slide">
          <div v-for="number in [currentIdx]" :key="number" transition="fade">
            <div class="slide" :style="{backgroundImage: 'url(' + require('~/assets/img/main/' + slideItems[currentIdx % slideItems.length].img) + ')'}"
              @mouseover="stopRataion"
              @mouseout="startRotation">
              <strong class="screen-out">{{slideItems[currentIdx % slideItems.length].desc}}</strong>
            </div>
          </div>
        </transition-group>
      <!-- </image-slider> -->
      <div>
        <v-btn class="btn-prev" v-ripple="false" icon @click="prev">
          <v-icon x-large color="rgba(255,255,255,0.2)">mdi-arrow-left-circle-outline</v-icon>
        </v-btn>
        <v-btn class="btn-next" v-ripple="false" icon @click="next">
          <v-icon x-large color="rgba(255,255,255,0.2)">mdi-arrow-right-circle-outline</v-icon>
        </v-btn>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        slideItems: [
          {
            desc: '마마미니 더치베이비',
            img: 'bnr_main.png'
          },
          {
            desc: '마마미니 크로플',
            img: 'bnr_main_v2.png'
          }
        ],
        currentIdx: 0,
        timer: null
      }
    },
    mounted() {
      this.startRotation();
    },
    methods: {
      startRotation() {
        this.timer = setInterval(() => this.next(), 2000);
      },
      stopRataion() {
        clearTimeout(this.timer);
        this.timer = null;
      },
      next() {
        this.currentIdx += 1;
      },
      prev() {
        this.currentIdx -= 1;
      }
    },
    computed: {
      currentImg() {
        return this.slideItems[Math.abs(this.currentIdx) % this.slideItems.length];
      }
    }
  }
</script>

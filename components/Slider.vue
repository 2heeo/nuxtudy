<template>
  <div>
    <div class="slider">
      <!-- <image-slider> -->
        <transition-group name="fade" tag="div" class="slide">
          <div v-for="number in [currentIdx]" :key="number" transition="fade">
            <!-- <div class="slide" :style="{background: `url(${require(slideItems[currentIdx % slideItems.length])}) no-repeat 50% 50% / cover`}"
              @mouseover="stopRataion"
              @mouseout="startRotation">
              <strong class="screen-out">{{slideItems[currentIdx % slideItems.length].desc}}</strong>
            </div> -->
          </div>
        </transition-group>
      <!-- </image-slider> -->
      <p>
        <v-btn class="btn-prev" v-ripple="false" icon @click="prev">
          <v-icon x-large color="rgba(0,0,0,0.2)">mdi-arrow-left-circle-outline</v-icon>
        </v-btn>
        <v-btn class="btn-next" v-ripple="false" icon @click="next">
          <v-icon x-large color="rgba(0,0,0,0.2)">mdi-arrow-right-circle-outline</v-icon>
        </v-btn>
      </p>
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
            img: '~/assets/img/main/bnr_main.png'
          },
          {
            desc: '마마미니 크로플',
            img: '~/assets/img/main/bnr_main_v2.png'
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
        this.timer = setInterval(() => this.next(), 3000);
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

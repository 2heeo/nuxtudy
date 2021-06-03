<template>
  <div class="list-menu">
    <h2 class="main-tit">Tip</h2>
    <v-row no-gutters justify="space-around">
      <v-col cols="3" class="d-flex justify-space-around">
        <v-card
          v-for="(menu, idx) in menuItems" :key="idx" class="ma-3">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
            height="300px"
          ></v-img>

          <v-card-title v-if="menu.tit !== ''">{{menu.tit}}</v-card-title>
          <v-card-subtitle v-if="menu.desc !== ''">{{menu.desc}}</v-card-subtitle>    
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        menuItems: [
          {
            tit: '메뉴 1',
            desc: '왜들 그리 다운돼있어? 뭐가 문제야 say something 분위기가 겁나 싸해 요새는 이런 게 유행인가 왜들 그리 재미없어? 아 그건 나도 마찬가지',
            img: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
          },
          {
            tit: '메뉴 2',
            desc: '메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.',
            img: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
          },
          {
            tit: '메뉴 3',
            desc: '메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.',
            img: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
          },
          {
            tit: '메뉴 4',
            desc: '메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.메뉴 입니다.',
            img: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
          }
        ]
      }
    }
  }
</script>
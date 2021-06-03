<template>
  <div class="image-link">
    <h2 class="main-tit">{{bnrTit}}</h2>
    <v-btn class="btn-link" nuxt to="/reserve" color="green white--text">자세히 알아보기</v-btn>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        bnrTit: '예약하기',
        bnrImg: ''
      }
    }
  }
</script>
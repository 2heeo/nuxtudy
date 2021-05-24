<template lang="pug">
  <div id="main">
    <header>
      <h1>
        <a href="javascript:;" class="ico_nuxtudy btn_logo">넉스터디</a>
      </h1>
      <nav>
        <h2 class="screen_out">넉스터디 메뉴</h2>
        <ul class="list_gnb">
          <li v-for="(menu, index) in menus" :class="{'on': index === 0}" @click="selectMenu">
            <a v-bind:href="menu.link">{{menu.tit}}</a>
          </li>          
        </ul>
      </nav>
      <a href="javascript:;" class="ico_nuxtudy btn_lang">
        <img src="~/assets/img/main/ico_lang.svg">
      </a>
    </header>
    <section>
      <article class="cont_bnr">
        <h3 class="screen_out">메인 배너</h3>
        <ul id="bnrList" class="list_bnr">
          <li v-for="banner in banners">
            <img :src="banner.src" alt="" /> <!-- todo: background-image로 변경 -->
          </li>
        </ul>
        <div class="list_idx">
          <button :class="{'on': index === 0}" v-for="(banner, index) in banners" @click="selectSlide">{{index}}</button>
        </div>
      </article>
      <article class="cont_reserve">
        <h3>예약 조회</h3>
      </article>
      <article class="cont_info">
        <h3>카페 정보</h3>
      </article>
      <article class="cont_tip">
        <h3>Tip 정보</h3>
        <ul class="list_tip">
          <li v-bind:style="{background: `url(${tip.src})`}" v-for="tip in tips"></li>
        </ul>
      </article>
    </section>
    <footer>
      <ul class="list_footer" v-for="footerList in footerDatas">
        <li v-for="(aa, index) in footerList.footerItems">
          <a v-bind:href="aa.link">{{aa.text}} {{index}}</a>
        </li>
      </ul>
    </footer>
  </div>
</template>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  export default  {
    // el: '#bnrList',
    data() {
      return {
        menus: [
          {
            tit: '디어노이',
            link: 'javascript:;'
          },
          {
            tit: '마마미니',
            link: 'javascript:;'
          },
          {
            tit: '메뉴 3',
            link: 'javascript:;'
          },
          {
            tit: '메뉴 4',
            link: 'javascript:;'
          }
        ],
        banners: [
          {src: 'https://dummyimage.com/1000x600/f0daf0/fff.png&text=slide+1'},
          {src: 'https://dummyimage.com/1000x600/d5d2f7/0011ff.png&text=slide+2'},
          {src: 'https://dummyimage.com/1000x600/d2f5df/0011ff.png&text=slide+3'},
          {src: 'https://dummyimage.com/1000x600/f3f5c9/0011ff.png&text=slide+4'}
        ],
        tips: [
          {src: 'https://dummyimage.com/200x300/f0daf0/fff.png&text=tip+1'},
          {src: 'https://dummyimage.com/200x300/d5d2f7/0011ff.png&text=tip+2'},
          {src: 'https://dummyimage.com/200x300/d2f5df/0011ff.png&text=tip+3'},
          {src: 'https://dummyimage.com/200x300/f3f5c9/0011ff.png&text=tip+4'}
        ],
        footerDatas: [
          {
            footerItems: [
              {
                text: '디어노이',
                link: 'javascript:;'
              },
              {
                text: '디어노이',
                link: 'javascript:;'
              },
              {
                text: '디어노이',
                link: 'javascript:;'
              }
            ]
          },
          {
            footerItems: [
              {
                text: '마마미니',
                link: 'javascript:;'
              },
              {
                text: '마마미니',
                link: 'javascript:;'
              },
              {
                text: '마마미니',
                link: 'javascript:;'
              },
              {
                text: '마마미니',
                link: 'javascript:;'
              }
            ]
          },
        ]
      }
    },
    methods: {
      selectMenu: (event) => {
        const {path} = event;
        const currentTarget = event.currentTarget;
        document.querySelector('.list_gnb .on').classList.remove('on');
        currentTarget.classList.add('on');
      },
      selectSlide: (event) => {
        const {path} = event;
        const currentTarget = event.currentTarget;
        const slider = document.querySelector('.cont_bnr');
        const bnrList = slider.querySelector('.list_bnr');
        const bnr = bnrList.querySelectorAll('li');
        const idxBtns = slider.querySelectorAll('.list_idx button');

        const clickedBtn = path.forEach((el) => {
          if(el?.classList?.contains('on')) { 
            return el;
          }
        });

        event.preventDefault();
        document.querySelector('.list_idx .on').classList.remove('on');
        currentTarget.classList.add('on');
        
        // console.log(currentTarget);
        // console.log(path);
        // console.log(clickedBtn);
        console.log(idxBtns);
        // console.log(idxBtns.indexOf(clickedBtn));

        // bnrList.animate({'margin-left': -(slider.width * idxButtons.indexOf(idxBtns), 500)});
      }
    }
  }
</script>
<template>
  <div class="main-flex-container">
    <div class="left-side"></div>

    <div class="main-content">
      <div class="section section-kv">
        <div class="section-inner">
          <div class="hamburger-menu" style="display: none;">
            <label class="menu__btn" for="menu__toggle" @click="menuOpen = true">
              <span></span>
            </label>
            <div class="menu__box" v-if="menuOpen">
              <ul class="menu__list">
                <li><a class="menu__item" href="#" @click="menuOpen = false">Home</a></li>
                <li><a class="menu__item" href="#" @click="menuOpen = false">About</a></li>
                <li><a class="menu__item" href="#" @click="menuOpen = false">Services</a></li>
                <li><a class="menu__item" href="#" @click="menuOpen = false">Contact</a></li>
              </ul>
            </div>
          </div>
          <div class="kv-text aos-animation">
            <img src="./assets/kv-letter.png">
            <!-- <h1>芳</h1> -->
            <!-- <p>ダミーのテキストです。ダミーのテキストです。ダミーのテキストです。</p> -->
          </div>
          <img src="./assets/kv.jpg" class="kv-bg">
        </div>
      </div>
      <div class="section section-hours">
        <div class="section-inner aos-animation">
          <h3>- Hours -<span></span></h3>
          <p>19時〜24時（変動あり）</p>
          <p>【貸切り可能】</p>
          <hr>
          <p>お休み：日月祝（変動あり）</p>
          <p>※お問い合せください</p>
        </div>
      </div>

      <div class="section section-price">
        <div class="section-inner aos-animation">
          <h3>- Price -<span></span></h3>
          <p>チャージ、カラオケ</p>
          <hr>
          【飲み放題】<br>
          ２時間、カラオケ歌い放題（ビール別料金）（おつまみあり）<br><br>
          男性:4000円<br>
          女性:3500円
          <!-- <p>大人：２３０円<br>子供１２０円</p> -->
        </div>
      </div>

      <div class="section section-menu">
        <div class="section-inner">
          
          <div class="aos-animation">
            <h3>- Menu -</h3>
            <h2>【Bottle】</h2>
            <ul>
              <li>ウイスキー</li>
              <li>焼酎</li>
              <li>ワイン</li>
            </ul>
          </div>

          <div class="aos-animation">
            <h2>【Glass】</h2>
            <ul>
              <li>ビール（生）</li>
              <li>ウイスキー</li>
              <li>焼酎</li>
              <li>ワイン</li>
              <li>日本酒</li>
              <li>瓶ビール</li>
            </ul>
          </div>

          <div class="aos-animation">
            <h2>【Collections】</h2>
            <div class="drink-wrapper">
              <template  v-for="(item, index) in drinks" :key="index">
                <div class="drink-container">
                  <img :src="item.imgSrc" :alt="item.name">
                  <!-- <span>{{ item.name }}: {{ item.price }}円（税込）</span> -->
                </div>
              </template>
            </div>
          </div>
  
  
        </div>
      </div>
      <div class="section section-inside">
        <div class="section-inner">
          <h3>- Inside -</h3>
          <div class="image-container">
            <img src="./assets/inside/inside-1.jpg" class="aos-animation">
            <img src="./assets/inside/inside-2.jpg" class="aos-animation">
            <img src="./assets/inside/inside-3.jpg?v=20240612" class="aos-animation">
            <img src="./assets/inside/inside-4.jpg?v=20240612" class="aos-animation">
            <img src="./assets/inside/inside-5.jpg?v=20240612" class="aos-animation">
            <img src="./assets/inside/inside-6.jpg?v=20240612" class="aos-animation">
          </div>
        </div>
      </div>
      <div class="section section-location">
        <div class="section-inner aos-animation">
          <h3>- Access -</h3>
          <h2>〒063-0811札幌市西区琴似<br>1条4丁目4-21タケダビル2F</h2>
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2914.314766162808!2d141.3043865!3d43.0768774!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x5f0b284ea53ae893%3A0x4750c6f721882ee1!2z44CSMDYzLTA4MTEgSG9ra2FpZG8sIFNhcHBvcm8sIE5pc2hpIFdhcmQsIEtvdG9uaSAxIErFjSwgNC1jaMWNbWXiiJI04oiSMjEg44K_44Kx44OA44OT44Or!5e0!3m2!1sen!2sjp!4v1708440322308!5m2!1sen!2sjp" width="350" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
      </div>
    </div>

    <div class="right-side"></div>
  </div>
</template>


<script>
import AOS from 'aos'
import 'aos/dist/aos.css'

  export default {
    data() {
      return {
        twitterWidgetUrl: 'https://platform.twitter.com/widgets.js',
        menuOpen: false,
        drinks: [],
      };
    },
    methods: {
      
      // loadTwitterWidget() {
      //   if (!document.querySelector(`script[src="${this.twitterWidgetUrl}"]`)) {
      //     const script = document.createElement('script');
      //     script.setAttribute('src', this.twitterWidgetUrl);
      //     script.setAttribute('async', '');
      //     script.setAttribute('charset', 'utf-8');
      //     document.head.appendChild(script);
      //   }
      // },
      // addTimeline() {
      //   const timeline = document.createElement('a');
      //   timeline.className = 'twitter-timeline';
      //   timeline.href = 'https://twitter.com/pokemongo_db?ref_src=twsrc%5Etfw';
      //   timeline.innerText = 'Tweets by pokemongo_db';
      //   this.$refs.twitterEmbed.appendChild(timeline);
      // }
      addAosAttributes() {
        const fadeInElements = document.querySelectorAll('.aos-animation');
        fadeInElements.forEach(element => {
          element.setAttribute('data-aos', 'fade-zoom-in');
          element.setAttribute('data-aos-easing', 'ease-in-back');
          element.setAttribute('data-aos-delay', '250');
          element.setAttribute('data-aos-duration', '1000');
          element.setAttribute('data-aos-offset', '0');
          element.setAttribute('data-aos-once', 'true');
        });
      } 
    },
    mounted() {
      this.addAosAttributes()
      AOS.init()
      // this.loadTwitterWidget();
      // this.addTimeline();
      // this.$nextTick(() => {
      //   window.twttr && window.twttr.widgets && window.twttr.widgets.load();
      // });
      this.drinks.push(
        {imgSrc: require('@/assets/drinks/drink-1.jpg'), price:null,name:'sake-1', type: 'bottle'},
        {imgSrc: require('@/assets/drinks/drink-2.jpg'), price:null,name:'sake-2', type: 'bottle'},
        {imgSrc: require('@/assets/drinks/drink-3.jpg'), price:null,name:'sake-3', type: 'bottle'},
        {imgSrc: require('@/assets/drinks/drink-4.jpg'), price:null,name:'sake-3', type: 'bottle'},
        {imgSrc: require('@/assets/drinks/drink-5.jpg'), price:null,name:'sake-3', type: 'bottle'},
        {imgSrc: require('@/assets/drinks/drink-6.jpg'), price:null,name:'sake-3', type: 'bottle'},
        {imgSrc: require('@/assets/drinks/drink-7.jpg'), price:null,name:'sake-3', type: 'bottle'},

      )
    },
    watch: {
      menuOpen(newVal) {
        if (newVal) {
          document.body.style.overflow = 'hidden';
        } else {
          document.body.style.overflow = 'auto';
        }
      },
    },
  }
</script>

<style>
  html,body{
    margin: 0;
    padding: 0;

    font-family: 'Noto Sans JP', sans-serif;
  }

  img{
    max-width: 100%;
  }

  .main-flex-container{
    display: flex;
  }
  .left-side,
  .right-side,
  .main-content{
    min-height: 100vh;
    
  }

  .main-content{
    box-shadow: -4px 4px 8px rgba(0, 0, 0, 0.2),
                4px 4px 8px rgba(0, 0, 0, 0.2);

  }
  
  .main-content{
    position: relative;
    overflow: hidden;
  }
  .left-side,
  .right-side {
    width: calc((100vw - 650px) / 2);
  }
  .left-side{
    /* background: red; */
  }

  .right-side{
    /* background: blue; */
  }

  



  

  .main-content {
    width: 650px;
  }

  .hamburger-menu {
    position: relative;
    z-index: 20;
  }

  .menu__toggle {
      opacity: 0;
  }

  .menu__btn {
      display: flex;
      align-items: center;
      position: absolute;
      top: 20px;
      left: 20px;
      width: 26px;
      height: 26px;
      cursor: pointer;
      z-index: 1;
  }

  .menu__btn > span,
  .menu__btn > span::before,
  .menu__btn > span::after {
      display: block;
      position: absolute;
      width: 100%;
      height: 2px;
      background-color: white;
  }

  .menu__btn > span::before {
      content: '';
      top: -8px;
  }

  .menu__btn > span::after {
      content: '';
      top: 8px;
  }

  .menu__box {
      /* display: none; */
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-color: rgba(0, 0, 0, 0.8);
      z-index: 2;
  }

  .menu__list {
      list-style: none;
      padding: 0;
      margin: 0;
      text-align: center;
      padding-top: 100px;
  }

  .menu__item {
      padding: 10px;
      font-size: 20px;
      color: #fff;
      text-decoration: none;
  }

  .menu__toggle:checked ~ .menu__box {
      display: block;
  }

  .main-content .section{
    padding: 20px 5%;
  }

  .main-content .section:nth-child(even){
    background: #67729D;
    color: white;
  }

  .main-content .section-kv{
    position: relative;
    display: block;
    width: 100%;
    aspect-ratio: 5/4;

    padding: 0;

  }

  .main-content .section-kv .kv-text{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -47.5%);

    height: 65%;

    z-index: 15;

    color: white;
    font-weight: bold;

    
  }

  .main-content .section-kv .kv-text img {
    text-align: center;
    font-size: 100px;

    font-family: serif;

    text-shadow: 4px 4px 8px rgba(0, 0, 0, 0.5);
    /* display: flex;
    align-content: center;
    justify-content: center; */

    filter: brightness(0) invert(1) drop-shadow(5px 5px 5px rgba(0, 0, 0, 0.5));
    height: 100%;
  }

  .main-content .section-kv .kv-bg{
    display: block;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    height: 100%;

    z-index: 10;

    filter: brightness(50%);
  }

  .main-content h3{
    font-family: "Lobster", sans-serif;
    font-weight: 400;
    font-style: normal;

    font-size: 2.5em;

    display: flex;
    gap: 10px;
    align-items: flex-end ;
    /* align-items: center; */
  }

  .main-content h3 span{
    font-size: .4em;
  }

  /* ------------------------ */

  .main-content .section-menu h2{
    font-family: "Lobster", sans-serif;
    font-weight: 400;
    font-style: normal;
  }

  .main-content .section-menu .drink-wrapper{
    display: flex;
    overflow-x: scroll;

    padding: 0 20px 20px;
  }

  .main-content .section-menu .drink-wrapper .drink-container{
    display: block;
    margin-right: 25px;

    
  }

  .main-content .section-menu .drink-wrapper .drink-container img{
    display: block;
    max-width: unset;
    width: 225px;
    height: auto;

    /* margin-bottom: 20px; */

    border: 2px solid #BB9CC0;
  }

  .main-content .section-inside .image-container{
    display: grid;
    margin: auto;
    grid-template-columns: repeat(2,49%);
    gap: 15px;
    justify-content: space-between;
  }

  .main-content .section-inside .image-container img{
    display: block;
    border: 2px solid #BB9CC0;
  }
  
  .section-location{
    text-align: center;
  }

  @media screen and (max-width: 650px) {
    .main-content {
      width: 100vw;
    }
  }
</style>

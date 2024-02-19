<template>
  <div class="main-flex-container">
    <div class="left-side"></div>
    <div class="main-content">
      <div class="section section-kv">
        <div class="hamburger-menu">
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

        <h1>芳</h1>
        <p>ダミーのテキストです。ダミーのテキストです。ダミーのテキストです。</p>
      </div>
      <div class="section section-hours">
        <h3>Hours</h3>
        <p>17:00-25:00</p>
      </div>
      <div class="section section-price">
        <h3>値段</h3>
        <p>大人：２３０円<br>子供１２０円</p>
      </div>
      <div class="section section-location">
        <h3>アクセス</h3>
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2914.314581179221!2d141.3018115765611!3d43.07688128951376!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x5f0b284ea53ae893%3A0x4750c6f721882ee1!2z44CSMDYzLTA4MTEgSG9ra2FpZG8sIFNhcHBvcm8sIE5pc2hpIFdhcmQsIEtvdG9uaSAxIErFjSwgNC1jaMWNbWXiiJI04oiSMjEg44K_44Kx44OA44OT44Or!5e0!3m2!1sen!2sjp!4v1708171340788!5m2!1sen!2sjp" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
    </div>
    <div class="right-side"></div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        twitterWidgetUrl: 'https://platform.twitter.com/widgets.js',
        menuOpen: false,
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
    },
    mounted() {
      // this.loadTwitterWidget();
      // this.addTimeline();
      // this.$nextTick(() => {
      //   window.twttr && window.twttr.widgets && window.twttr.widgets.load();
      // });
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
  }
  .main-flex-container{
    display: flex;
  }
  .left-side,
  .right-side,
  .main-content{
    min-height: 100vh;
  }
  .left-side,
  .right-side {
    width: calc((100vw - 650px) / 2);
  }
  .left-side{
    background: red;
  }

  .right-side{
    background: blue;
  }

  

  .main-content {
    width: 650px;
  }

  .hamburger-menu {
    position: relative;
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
      background-color: #333;
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
      background: purple;
    }

    .main-content .section-kv h1 {
      text-align: center;
      /* display: flex;
      align-content: center;
      justify-content: center; */
    }

  @media screen and (max-width: 650px) {
    .main-content {
      width: 100vw;
    }
  }
</style>

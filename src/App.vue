<template>
   <h1>しんたままのサイト</h1>
  <!-- <div ref="twitterEmbed"></div> -->
</template>

<script>
export default {
  data() {
    return {
      twitterWidgetUrl: 'https://platform.twitter.com/widgets.js'
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
  }
}
</script>

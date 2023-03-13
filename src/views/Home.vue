<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <swiper>
        <swiper-slide>Slide 1</swiper-slide>
        <swiper-slide>Slide 2</swiper-slide>
        <swiper-slide>Slide 3</swiper-slide>
      </swiper>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonicSlides } from '@ionic/vue';
import { defineComponent } from 'vue';
import { Autoplay, Keyboard, Pagination, Scrollbar, Zoom } from 'swiper';
import { Swiper, SwiperSlide } from 'swiper/vue/swiper-vue.js';

// import 'swiper/swiper.min.css';
import 'swiper/css'; // error
import 'swiper/modules/autoplay/autoplay.min.css';
import 'swiper/modules/keyboard/keyboard.min.css';
import 'swiper/modules/pagination/pagination.min.css';
import 'swiper/modules/scrollbar/scrollbar.min.css';
import 'swiper/modules/zoom/zoom.min.css';
import 'swiper/modules/effect-fade/effect-fade.min.css';
import '@ionic/vue/css/ionic-swiper.css';

export default defineComponent({
  name: 'Home',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    Swiper,
    SwiperSlide
  },
  setup() {
    return {
      modules: [Autoplay, Keyboard, Pagination, Scrollbar, Zoom, IonicSlides],
    }
  }
});
</script>

<style scoped>

</style>
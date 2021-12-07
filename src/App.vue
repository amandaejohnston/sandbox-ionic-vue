<template>
  <ion-app>
    <ion-page>
      <ion-header>
        <ion-toolbar>
          <ion-title>Header</ion-title>
          <ion-buttons slot="end">
            <ion-button @click="presentInlineModal()">Inline</ion-button>
            <ion-button @click="presentControllerModal()">Controller</ion-button>
          </ion-buttons>
        </ion-toolbar>
      </ion-header>
      <ion-content>Content</ion-content>
      <ion-modal :is-open="isOpenRef" @didDismiss="setOpen(false)">
        <Modal></Modal>
      </ion-modal>
    </ion-page>
  </ion-app>
</template>

<script lang="ts">
import { IonApp, IonPage, IonHeader, IonModal, IonToolbar, IonTitle, IonButtons, IonButton, IonContent, modalController } from '@ionic/vue';
import { defineComponent, ref } from 'vue';
import Modal from './components/Modal.vue';

export default defineComponent({
  name: 'App',
  components: {
    IonApp,
    IonPage,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonButtons,
    IonButton,
    IonContent,
    IonModal,
    Modal
  },
  setup() {
    const isOpenRef = ref(false);
    const setOpen = (state: boolean) => isOpenRef.value = state;

    const presentControllerModal = async () => {
      const modal = await modalController.create({
        component: Modal
      });
      return modal.present();
    };

    const presentInlineModal = () => {
      setOpen(true);
    };

    return {
      presentControllerModal,
      presentInlineModal,
      setOpen,
      isOpenRef
    };
  }
});
</script>
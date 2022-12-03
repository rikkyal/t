<template>
  <div class="ion-page">
    <ion-header>
      <ion-toolbar class="toolbar-md-primary"> 
        <ion-title>SocialSharing RikkyAl</ion-title>
    </ion-toolbar>
  </ion-header>
  <ion-content padding>
    <p><strong>{{ text }}</strong></p>
    <p><ion-img class="img-wrapper" :src="imgUrl"></ion-img></p>
    <p><a href="url">Universitas Terbuka</a></p> 
  <ion-button @click="kirimKeWhatsApp(text, imgUrl, url)">Share melalui WhatsApp</ion-button>
  </ion-content>
</div>
</template>

<script lang="ts">
import { IonButton, IonHeader, IonContent, IonImg, IonToolbar, IonTitle } from '@ionic/vue';
import { SocialSharing } from '@awesome-cordova-plugins/social-sharing';

export default {
name: "SocialSharingComponent",
data() { 
  return {
    text: 'Universitas Terbuka',
    imgUrl: 'https://www.ut.ac.id/sites/all/files/Logo-UT_03.png', 
    url: 'https://www.ut.ac.id/en'
  }
},
methods: {
    kirimKeWhatsApp(t:string, i:string, u:string){
      SocialSharing.shareViaWhatsApp(t, i, u);
    }
  },

components: { 
  IonImg, 
  IonHeader, 
  IonContent, 
  IonToolbar,
  IonButton,
  IonTitle
}
}
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>

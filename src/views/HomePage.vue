<template>
  <ion-page>
    <ion-header class="header" mode="ios">
      <ion-toolbar color="danger">
        <ion-buttons slot="start">
          <ion-back-button text="" :icon="chevronBackOutline"></ion-back-button>
        </ion-buttons>
        <ion-title class="text-light ion-padding-center">Touring Packge </ion-title>
      </ion-toolbar>
    </ion-header>

  <ion-content color="tertiary">
    <ion-searchbar mode="ios"></ion-searchbar>
      <ion-card>
        <ion-card-content color="tertiary">
          <div class="ion-no-margin">
            <ion-list v-for="pagkage in pagkages" :key="pagkage.image">
              <ion-card color="tertiary" class="ion-no-padding border-radius">
                      <ion-img :src="pagkage.image"></ion-img>
                      <ion-grid>
                        <ion-row>
                          <ion-col size="7">
                            <ion-label>
                              <h2><b>{{pagkage.englishname}}</b></h2>
                              <h3>{{pagkage.thainame}}</h3>
                            </ion-label>
                          </ion-col>
                          <ion-col size="5">
                            <ion-label>
                              <h3 class="ion-text-right">
                                <ion-text color="danger">
                                  <h2>
                                    {{pagkage.price}}<small>&nbsp;THB</small><span>/คน</span>
                                  </h2>
                                </ion-text>
                                <ion-text color="medium">
                                  ราคารวมภาษีแล้ว
                                </ion-text>
                              </h3>
                            </ion-label>
                          </ion-col>
                        </ion-row>
                      </ion-grid>
                      <ion-card-content style="text-align: left;">
                          <ion-icon :icon="busOutline"></ion-icon>&nbsp;{{pagkage.icon1}}<br>
                          <ion-icon :icon="bedOutline"></ion-icon>&nbsp;{{pagkage.icon2}}<br>
                          <ion-icon :icon="fastFoodOutline"></ion-icon>&nbsp;{{pagkage.icon3}}<br>
                      </ion-card-content>
                    <ion-button color="danger" class="ion-no-margin" expand="full" @click="() => router.push('/TourDetail')">เลือก</ion-button>
              </ion-card>
            </ion-list>
          </div>
        </ion-card-content>
    </ion-card>
  </ion-content>
  


  </ion-page>
</template>

<script>
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonButtons,
  IonBackButton,
  IonCard,
  IonList,
  IonItem,
  IonInput,
  IonButton,
  IonLabel, 
  IonTabBar, 
  IonTabButton, 
  IonTabs,
  IonFooter,
  IonIcon, 
  IonCol,
  IonGrid,
  IonRow
} from '@ionic/vue';
import { defineComponent } from 'vue';
import { busOutline,bedOutline,fastFoodOutline,alertCircleOutline,chevronBackOutline } from 'ionicons/icons';
import { useRouter } from "vue-router";

export default defineComponent({
  name: 'HomePage',
  components: {
    IonPage,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonButtons,
    IonBackButton, 
    IonCard,
    IonIcon, 
    IonCol,
    IonGrid,
    IonRow
  },
  setup() {
    const router = useRouter();
    
    const pagkages = [
    { 'thainame': 'ไร่เลย์ เบย์ รีสอร์ท แอนด์ สปา',
     'englishname': 'Railay Bay Resort',
     'icon1': 'รถรับส่งส่วนตัว',
     'icon2': 'พักรีสอร์ทติดหาดติดหาดไร่เลย์ ',
     'icon3': 'อาหารเช้าแบบบุฟเฟ่ต์ 2 มื้อ',
     'image': 'https://itp1.itopfile.com/ImageServer/itp_17012020ybvl/0/0/Home-Recommend-3z-z877547007295.jpg',
     'price': '2,590'} ,
     {'thainame': 'เคซี แกรนด์ รีสอร์ท แอนด์ สปา',
     'englishname': 'KC Grande Resort',
     'icon1': 'รถรับส่งส่วนตัว',
     'icon2': 'พักผ่อนติดเกาะหย่อนใจ',
     'icon3': 'อาหารเช้าแบบบุฟเฟ่ต์ 2 มื้อ',
     'image': 'https://itp1.itopfile.com/ImageServer/itp_17012020ybvl/1610/0/Home-Recommend-1z-z1094936940018.jpg',
     'price': '3,390'} ,
     {'thainame': 'ทรายแก้ว บีช รีสอร์ท',
     'englishname': 'Sai Keaw Beach Resort',
     'icon1': 'รถรับส่งส่วนตัว',
     'icon2': 'พักรีสอร์ทติดหาดติดหาดไร่เลย์ ',
     'icon3': 'พร้อมอาหารเช้าแบบบุฟเฟ่ต์ 2 มื้อ',
     'image': 'https://itp1.itopfile.com/ImageServer/itp_17012020ybvl/0/0/Home-Recommend-3z-z877547007295.jpg',
     'price': '2,590'} ,
     {'thainame': 'โนโวเทล ระยอง ริมแพ รีสอร์ท',
     'englishname': 'NovotelRayong Rimpae',
     'icon1': 'รถรับส่งส่วนตัว',
     'icon2': 'พักรีสอร์ทติดหาดติดหาดไร่เลย์ ',
     'icon3': 'พร้อมอาหารเช้าแบบบุฟเฟ่ต์ 2 มื้อ',
     'image': 'https://itp1.itopfile.com/ImageServer/itp_17012020ybvl/526/0/Novotel-19-5-65z-z257763485456.jpg',
     'price': '1,145'}
    ];
    
    return {
      router,
      busOutline,
      bedOutline,
      fastFoodOutline,
      alertCircleOutline,
      chevronBackOutline,
      pagkages
    }
  }
});
</script>

<style scoped>
.cardpromo {
  height: 300px;
}
.imgpromo {
  height: 220px;
}
ion-searchbar {
  margin: auto;
  width: 100%;
  border-radius: 1px;
}
</style>
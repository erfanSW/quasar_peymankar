<template>
  <q-layout class="hHh lpr fff">
    <q-header>
      <q-toolbar class="bg-grey-11 text-primary vertical-middle">
        <q-btn class="fullborder" size="35px" @click="left = !left" flat round dense>
          <img :src="'statics/auction.png'" alt />
        </q-btn>
        <q-btn size="20px" class="border gt-sm" flat dense>پیمانکار</q-btn>
        <q-btn size="20px" class="border gt-sm" flat dense>مناقصات</q-btn>
        <q-btn size="20px" class="border gt-sm" flat dense>مزایده ها</q-btn>
        <q-btn size="20px" class="border gt-sm" flat dense>
          <!-- <img width="40px" :src="'statics/team.png'" /> -->
          درباره ما
        </q-btn>
        <q-btn size="20px" class="border gt-sm" flat dense>
          پرسشهای متداول
          <!-- <img width="40px" :src="'statics/question.png'" /> -->
        </q-btn>
        <!-- <q-btn size="20px" style="margin-left:26px" class="loginborder" flat dense>ورود/ثبت نام</q-btn> -->
        <q-toolbar-title size="28px" flat dense></q-toolbar-title>
        <q-btn size="15px" style="margin-left:26px" class="loginborder" flat dense>ورود/ثبت نام</q-btn>
      </q-toolbar>
    </q-header>
    <q-drawer
      v-model="left"
      class="bg-grey-11 text-primary lt-md"
      side="left"
      :width="200"
      :breakpoint="400"
      show-if-above
    >
      <!-- <q-item class="lt-md">
        <q-item-section>
          <q-btn class="fullborder" size="35px" @click="left = !left" flat round dense>
            <img :src="'statics/auction.png'" alt />
          </q-btn>
        </q-item-section>
      </q-item>-->
      <q-list class="bg-grey-11 lt-md">
        <q-item>
          <q-item-section avatar>
            <img width="40px" :src="'statics/tender.png'" />
          </q-item-section>
          <q-item-section>مناقصات</q-item-section>
        </q-item>
        <q-item>
          <q-item-section avatar>
            <img width="40px" :src="'statics/auction_2.png'" />
          </q-item-section>
          <q-item-section>مزایده ها</q-item-section>
        </q-item>
        <q-item>
          <q-item-section avatar>
            <img width="40px" :src="'statics/team.png'" />
          </q-item-section>
          <q-item-section>درباره ما</q-item-section>
        </q-item>
        <q-item>
          <q-item-section avatar>
            <img width="40px" :src="'statics/question.png'" />
          </q-item-section>
          <q-item-section>پرسشهای متداول</q-item-section>
        </q-item>
      </q-list>
    </q-drawer>
    <q-drawer>
      <div style="max-width: 250px;margin-top:40px;margin-right:20px;">
        <q-list bordered>
          <q-item-label header>فهرست موضوعات</q-item-label>
          <q-item v-for="contact in contacts" :key="contact.id" class="q-my-sm" clickable v-ripple>
            <q-item-section avatar>
              <q-avatar>
                <q-img :src="contact.image"></q-img>
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ contact.name }}</q-item-label>
              <q-item-label caption lines="1">{{ contact.email }}</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </div>
    </q-drawer>
    <!-- <div style="max-width: 250px;margin-top:40px;margin-right:20px;">
      <q-list bordered>
        <q-item-label header>فهرست موضوعات</q-item-label>
        <q-item v-for="contact in contacts" :key="contact.id" class="q-my-sm" clickable v-ripple>
          <q-item-section avatar>
            <q-avatar>
              <q-img :src="contact.image"></q-img>
            </q-avatar>
          </q-item-section>
          <q-item-section>
            <q-item-label>{{ contact.name }}</q-item-label>
            <q-item-label caption lines="1">{{ contact.email }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </div>-->
    
    <q-page-container>
     <!-- <div style="max-width: 250px;margin-top:40px;margin-right:0px;margin-top:-10px;">
      <q-list bordered>
        <q-item-label header>فهرست موضوعات</q-item-label>
        <q-item v-for="contact in contacts" :key="contact.id" class="q-my-sm" clickable v-ripple>
          <q-item-section avatar>
            <q-avatar>
              <q-img :src="contact.image"></q-img>
            </q-avatar>
          </q-item-section>
          <q-item-section>
            <q-item-label>{{ contact.name }}</q-item-label>
            <q-item-label caption lines="1">{{ contact.email }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </div> -->
      <router-view></router-view>
    </q-page-container>
  </q-layout>
</template>

<script>
import { openURL } from "quasar";

export default {
  name: "MyLayout",
  data() {
    return {
      left: false,
      contacts: [
        {
          id: 1,
          name: "اقتصادی",
          image: "statics/justice.png"
        },
        {
          id: 2,
          name: "عمران",
          image: "statics/civil.png"
        },
        {
          id: 3,
          name: "حمل و نقل",
          image: "statics/transportation.png"
        },
        {
          id: 4,
          name: "فرهنگی",
          image: "statics/cultural.png"
        },
        {
          id: 5,
          name: "حسابداری",
          image: "statics/accounting.png"
        },
        {
          id: 6,
          name: "فضای سبز",
          image: "statics/park.png"
        },
        {
          id: 7,
          name: "فناوری و اطلاعات",
          image: "statics/it.png"
        },
        {
          id: 8,
          name: "مطالعاتی و مشاوره ای",
          image: "statics/call.png"
        }
      ]
    };
  },
  methods: {
    openURL
  }
};
</script>

<style>
.border {
  margin-left: 14px;
}
.border:hover {
  border-bottom: 4px solid rgb(233, 30, 90);
  transform: scale(1.1, 1.1);
  border-radius: 2px;
  /* background-image: linear-gradient(to right,  #c77c8d , #ff8e97 ); */
}
.fullborder:hover {
  border: 4px solid rgb(233, 30, 90);
  transform: rotate(-360deg);
  /* transform: scale(0.7,0.7); */
  transition-delay: 150ms;
}
.loginborder {
  border: 2px solid rgb(233, 30, 90);
  border-radius: 15px;
  padding: 5px;
  /* background-image: linear-gradient(to right,  #c77c8d , #ff8e97 ); */
}
.loginborder:hover {
  /* background-color: green; */
  /* color: white; */
  transition-delay: 50ms;
  transition: 90deg;
  transform: scale(1.2, 1.2);
}
.drawer {
  background-color: rgb(180, 51, 51);
}
</style>

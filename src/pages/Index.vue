<template>
  <div class="row">
    <div class="col-xs-12 col-lg-2 col-md-2 gt-sm index">
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
            <q-item-label caption lines="1">{{ contact.count }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
      
    </div>
    <q-select
        class="xs"
        label="Flip up/down"
        transition-show="flip-up"
        transition-hide="flip-down"
        filled
        v-model="model"
        :options="contacts"
        style="width: 250px"
      />
    <div class="col-xs-12 col-lg-10 col-md-10 q-px-lg q-pb-md">
      <q-timeline :layout="layout" color="blue">
        <q-timeline-entry title="قابل توجه پیمانکاران محترم" subtitle="مرداد ۱۳۹۸"></q-timeline-entry>
        <q-timeline-entry side="right">
          <div>شرکت هایی که قصد ثبت نام در سامانه مدیریت قراردادها را دارند توجه فرمایند در هنگام ثبت نام از شماره تلفن همرایی استفاده نمایند که سرویس دریافت پیامک آن فعال باشد</div>
        </q-timeline-entry>
        <q-timeline-entry side="left">
          <div>جهت استفاده بهتر از امکانات این سامانه از مرورگر Mozila Firefox استفاده نمایید</div>
        </q-timeline-entry>
        <q-timeline-entry side="right">
          <div>جهت دریافت اسناد مناقصه یا مزایده ابتدا باید ثبت نام نموده و پس از تایید اطلاعات (حداکثر یک روز کاری) نام کاربری و کلمه عبور به تلفن همراه شما ارسال می گردد</div>
        </q-timeline-entry>
        <q-timeline-entry>
          <div>
            اطلاعات ثبتی شهرداری مرکزی اهواز جهت ارائه به نهادها و ارگانهای ذیربط عبارتند از:
            <pre>
کد اقتصادی: 411369653593
شناسه ملی: 14000167358
شماره ثبت: 1111
کد پستی:6133833159
            </pre>
          </div>
        </q-timeline-entry>
      </q-timeline>
    </div>
  </div>
</template>



<script>
export default {
  data() {
    return {
      contacts: [
        {
          id: 1,
          name: "اقتصادی",
          image: "statics/justice.png",
          count: 4
        },
        {
          id: 2,
          name: "عمران",
          image: "statics/civil.png",
          count: 12
        },
        {
          id: 3,
          name: "حمل و نقل",
          image: "statics/transportation.png",
          count: 25
        },
        {
          id: 4,
          name: "فرهنگی",
          image: "statics/cultural.png",
          count: 47
        },
        {
          id: 5,
          name: "حسابداری",
          image: "statics/accounting.png",
          count: 39
        },
        {
          id: 6,
          name: "فضای سبز",
          image: "statics/park.png",
          count: 21
        },
        {
          id: 7,
          name: "فناوری و اطلاعات",
          image: "statics/it.png",
          count: 13
        },
        {
          id: 8,
          name: "مطالعاتی و مشاوره ای",
          image: "statics/call.png",
          count: 51
        }
      ]
    };
  },
  name: "PageIndex"
};
</script>

<style scoped>
.index {
  max-width: 250px;
  margin-top: 40px;
  margin-right: 0px;
  margin-top: -10px;
}
pre:hover {
  margin-left: 20px;
  transform: scale(1.1, 1.1);
  transition-delay: 120ms;
  transition-timing-function: linear;
  /* background-image: linear-gradient(to right,  #c77c8d , #ff8e97 ); */
}
.timeline {
  background-image: linear-gradient(to left, #c77c8d, #ff8e97, #ffac9f);
}
</style>
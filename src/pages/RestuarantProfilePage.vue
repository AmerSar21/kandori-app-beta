<template>
  <q-page>
    <div class="q-pa-md text-left">
      <q-btn label="back" to="/" flat></q-btn>
    </div>
    <div class="container text-center">
      <q-card class="header-content no-shadow">
        <q-card-section class="q-pa-none">
          <q-img src="~assets/images/restoprof.jpg" style="height: 300px;" />
        </q-card-section>
        <q-card-section class="main-content q-pa-none">
          <q-avatar size="150px">
            <img src="~assets/images/restoprof.jpg" />
          </q-avatar>
          <q-separator spaced inset vertical dark />

          <q-item-label>
            <b>Food Court</b>
          </q-item-label>
          <p>"You'll find your cravings here!!"</p>
          <q-btn color="primary" label="Order Now"></q-btn>

          <q-tabs
            v-model="tab"
            dense
            class="text-grey q-pt-xl"
            active-color="primary"
            indicator-color="primary"
            align="justify"
            narrow-indicator
          >
            <q-tab name="home" label="Home" />
            <q-tab name="menu" label="Best Sellers" />
            <q-tab name="photos" label="Photos" />
            <q-tab name="reviews" label="Reviews" />
          </q-tabs>

          <q-separator />

          <q-tab-panels v-model="tab" animated>
            <q-tab-panel name="home">
              <div class="text-h6">Home</div>
              <div class="row">
                <div class="col q-pa-md">
                  <b>Description</b>
                  <p class="text-justify">
                    The food court provides you different types of foods that
                    may be snacks, meals or street foods. With the perfect
                    location and environment. With the Food Court it will take
                    you too the different..
                  </p>
                </div>
                <div class="col q-pa-md">
                  <b>History</b>
                  <p class="text-justify">
                    The food court was established in the year 2016. It started
                    as a little vendor shop in Mindanao State University - main
                    campus. Most of the students of the CBAA..
                  </p>
                </div>
              </div>
            </q-tab-panel>

            <q-tab-panel name="menu">
              <div class="text-h6">Best Sellers</div>
              <div class="row q-pa-sm">
                <p class="captions">
                  Signature Dishes: 1. The Food Court's Best: - Menu List: 1.
                  Street Foods - Isaw - Chicken Skin - Chicken Franks - tikolen
                  - Atay 2. Meals - Pater - Pater w/ palapa - Tapsilog -
                  Longsilog 3. Snacks - Chips - Beverages
                </p>
              </div>
            </q-tab-panel>

            <q-tab-panel name="photos">
              <div class="text-h6">Photos</div>
              <div class="q-pa-sm">
                <q-carousel
                  animated
                  v-model="slide"
                  navigation
                  infinite
                  :autoplay="autoplay"
                  arrows
                  transition-prev="slide-right"
                  transition-next="slide-left"
                  @mouseenter="autoplay = false"
                  @mouseleave="autoplay = true"
                >
                  <q-carousel-slide
                    :name="1"
                    img-src="~assets/images/food1.jpg"
                  />
                  <q-carousel-slide
                    :name="2"
                    img-src="~assets/images/food2.jpg"
                  />
                  <q-carousel-slide
                    :name="3"
                    img-src="~assets/images/food3.jpg"
                  />
                  <q-carousel-slide
                    :name="4"
                    img-src="~assets/images/food4.jpg"
                  />
                </q-carousel>
              </div>
            </q-tab-panel>
            <q-tab-panel name="reviews">
              <div class="text-h6">Reviews & Feed Backs</div>
              <div class="q-pa-md text-left" style="full-width">
                <q-list
                  v-for="(item, index) of Feedbacks"
                  :key="item.user"
                  v-bind="item"
                >
                  <q-item>
                    <q-item-section>
                      <q-item-label>{{ item.user }}</q-item-label>
                      <q-item-label caption lines="2"
                        >This restaurant is very good!!</q-item-label
                      >
                    </q-item-section>

                    <q-item-section side top>
                      <q-item-label caption>5 min ago</q-item-label>
                      <q-icon name="star" color="yellow" />
                    </q-item-section>
                  </q-item>

                  <q-separator spaced inset />
                </q-list>
                <br />
                <div class="q-pa-md">
                  <div class="q-gutter-y-md column" style="max-width: 300px">
                    <div class="text-h6">Email:</div>
                    <q-input
                      filled
                      v-model="email"
                      type="email"
                      suffix="@gmail.com"
                    >
                      <template v-slot:before>
                        <q-icon name="mail" />
                      </template>
                    </q-input>
                  </div>
                  <br />
                  <div class="text-h6">Comment:</div>
                  <br />
                  <q-input standout v-model="text" filled type="textarea" />
                  <br />
                  <div class="row">
                    <q-btn color="primary" icon-right="send" label="Submit">
                      <template v-slot:loading>
                        <q-spinner-facebook />
                      </template>
                    </q-btn>
                  </div>
                </div>
              </div>
            </q-tab-panel>
          </q-tab-panels>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script lang="ts">
import ExampleComponent from 'components/ClassComponent.vue';
import { Vue, Component } from 'vue-property-decorator';

@Component({
  components: { ExampleComponent }
})
export default class RestaurantProfilePage extends Vue {
  tab = 'home';
  slide = 1;
  autoplay = true;
  email = '';
  number = null;
  text = '';
  Feedbacks = [
    {
      user: 'John Carlos Laguna',
      description: 'This restaurant is very good!!'
    },
    {
      user: 'Anne Curtis',
      description: 'This restaurant is very good!!'
    },
    {
      user: 'Cristian Valdez',
      description: 'This restaurant is very good!!'
    },
    {
      user: 'Super Inggo',
      description: 'This restaurant is very good!!'
    },
    {
      user: 'Juan Ponce Enrile',
      description: 'This restaurant is very good!!'
    }
  ];
}
</script>

<style>
.bg-image {
  background-image: url('~assets/images/banner.jpg');
  background-repeat: no-repeat;
  background-size: contain;
}
.profile-name {
  font-size: 100% !important;
}
.main-content {
  position: relative;
  top: -80px;
}
img {
  border: 2px solid rgb(94, 93, 93);
}
.q-tab-panels {
  position: absolute;
  width: 100%;
}
</style>

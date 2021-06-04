<template>
  <q-page>
    <div class="q-pa-md text-center">
      <q-card>
        <q-img src="~assets/images/banner.jpg" style="height: 300px;"/>
      </q-card>
      <q-card class="q-pa-md">
        <q-card-section>
          <q-avatar size="150px">
            <img src="~assets/images/restoprof.jpg" />
          </q-avatar>
          <q-separator spaced inset vertical dark />
          <br />
          <b>Food Court</b>
          <p>"You'll find your cravings here!!"</p>
        </q-card-section>
        <q-card-actions class="row items-center justify-evenly">
          <q-btn color="primary" label="Order Now"></q-btn>
        </q-card-actions>
      </q-card>
      <br />
      <q-card>
        <q-tabs
          v-model="tab"
          dense
          class="text-grey"
          active-color="primary"
          indicator-color="primary"
          align="justify"
          narrow-indicator
        >
          <q-tab name="home" label="Home" />
          <q-tab name="menu" label="Signature" />
          <q-tab name="photos" label="Photos" />
          <q-tab name="reviews" label="Reviews" />
        </q-tabs>

        <q-separator />

        <q-tab-panels v-model="tab" animated>
          <q-tab-panel name="home">
            <div class="text-h6">Home</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </q-tab-panel>

          <q-tab-panel name="menu">
            <div class="text-h6">Signature Dishes</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </q-tab-panel>

          <q-tab-panel name="photos">
            <div class="text-h6">Photos</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </q-tab-panel>
          <q-tab-panel name="reviews">
            <div class="text-h6">Reviews</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </q-tab-panel>
        </q-tab-panels>
      </q-card>
      <br />
    </div>
  </q-page>
</template>

<script lang="ts">
export default {
  data() {
    return {
      tab: 'home'
    };
  }
};
</script>

<style>
.bg-image {
  background-image: url("~assets/images/banner.jpg");
  background-repeat: no-repeat;
  background-size: contain;
}
</style>

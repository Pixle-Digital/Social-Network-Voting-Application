<template>
  <div class="">
    <home-layout>
      <!-- Navbar -->

      <b-row class="">
        <b-card style="border-radius: 10px 10px 10px 10px; width: 100%">
          <b-row align-h="center">
            <!-- <b-colxx xl="6" lg="12">
        <icon-cards-carousel></icon-cards-carousel>
        <b-row>
          <b-colxx md="12" class="mb-4">
            <sales-chart-card></sales-chart-card>
          </b-colxx>
        </b-row>
      </b-colxx> -->
            <b-col cols="2">
              <b-card>
                <button type="button" class="btn btn-default">
                  <router-link to="preferences"> Preferences </router-link>
                </button>
              </b-card>
            </b-col>
            <b-col cols="2">
              <b-card>
                <button
                  type="button"
                  class="btn btn-default"
                  aria-label="Left Align"
                >
                  <router-link to="settings"> Settings </router-link>
                </button>
              </b-card>
            </b-col>
            <b-col cols="2">
              <b-card>
                <button
                  type="button"
                  class="btn btn-default"
                  aria-label="Left Align"
                >
                  <router-link to="awards"> Awards </router-link>
                </button>
              </b-card>
            </b-col>
          </b-row>
        </b-card>
      </b-row>
      <div class="row" style="background-color: ">
        <b-container class="bv-example-row">
          <b-row class="mt-5">
            <b-card style="border-radius: 10px 10px 10px 10px; width: 100%">

            </b-card>
          </b-row>
        </b-container>
      </div>
    </home-layout>
  </div>
</template>

<script>
import favouritesComponent from "../../../components/Qavah/favourites/favourites.vue";
import privatemode from "../../../components/Qavah/privatemode.vue";
import types from "../../../components/Qavah/search/types.vue";
export default {
  name: "awards",
  components: {
    favouritesComponent,
    privatemode,
    types,
  },
};
</script>

<style>
</style>

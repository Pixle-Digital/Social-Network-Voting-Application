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

            <b-colxx xxs="12" lg="4" class="mb-4 col-left">
                        <b-card no-body class="mb-4">
                            <div class="position-absolute card-top-buttons">
                                <b-button variant="outline-white" class="icon-button">
                                    <i class="simple-icon-pencil" />
                                </b-button>
                            </div>
                            <single-lightbox thumb="/assets/img/profiles/1.jpg" large="/assets/img/profiles/1.jpg" class-name="card-img-top" />
                            <b-card-body>
                                <p class="text-muted text-small mb-2">dawda</p>
                                <p class="mb-3">
                                    I’m a web developer. I spend my whole day, practically every day, experimenting with HTML, CSS,
                                    and JavaScript; dabbling with Python and Ruby; and inhaling a wide variety of potentially useless
                                    information through a few hundred RSS feeds. I build websites that delight and inform. I do it
                                    well.
                                </p>
                                <p class="text-muted text-small mb-2">dawda</p>
                                <p class="mb-3">Nairobi, Kenya</p>
                                <!-- <p class="text-muted text-small mb-2">adawda</p>
                                <p class="mb-3">
                                    <b-badge variant="outline-secondary" class="mb-1 mr-1" pill>32</b-badge>
                                    <b-badge variant="outline-secondary" class="mb-1 mr-1" pill>JAVASCRIPT</b-badge>
                                    <b-badge variant="outline-secondary" class="mb-1 mr-1" pill>SECURITY</b-badge>
                                    <b-badge variant="outline-secondary" class="mb-1 mr-1" pill>DESIGN</b-badge>
                                </p>
                                <p class="text-muted text-small mb-2">adawd</p>
                                <div class="social-icons">
                                    <ul class="list-unstyled list-inline">
                                        <li class="list-inline-item">
                                            <router-link to="#"><i class="simple-icon-social-facebook"></i></router-link>
                                        </li>
                                        <li class="list-inline-item">
                                            <router-link to="#"><i class="simple-icon-social-twitter"></i></router-link>
                                        </li>
                                        <li class="list-inline-item">
                                            <router-link to="#"><i class="simple-icon-social-instagram"></i></router-link>
                                        </li>
                                    </ul>
                                </div> -->
                            </b-card-body>
                        </b-card>

                    </b-colxx>

                    <b-colxx xxs="12" lg="8" class="mb-4 col-right">
                        <b-row>
    <b-colxx xxs="12">
      <b-card class="mb-4" title="Account Setting">
        <b-form
          @submit.prevent="onValitadeOverLineFormFormSubmit"
          class="av-tooltip tooltip-label-bottom"
        >
          <b-form-group :label="$t('forms.email')" class="has-float-label">
            <b-form-input
              type="text" disabled
              v-model.trim="$v.overLineForm.email.$model"
              :state="!$v.overLineForm.email.$error"
            />
            <b-form-invalid-feedback v-if="!$v.overLineForm.email.required">Email is required!</b-form-invalid-feedback>
            <b-form-invalid-feedback v-else-if="!$v.overLineForm.email.email">Invalid email address</b-form-invalid-feedback>
          </b-form-group>
            <b-form-group label="Username"  class="has-float-label">
            <b-form-input
              type="text" disabled
              v-model.trim="$v.overLineForm.email.$model"
              :state="!$v.overLineForm.email.$error"
            />
            <b-form-invalid-feedback v-if="!$v.overLineForm.email.required">Email is required!</b-form-invalid-feedback>
            <b-form-invalid-feedback v-else-if="!$v.overLineForm.email.email">Invalid email address</b-form-invalid-feedback>
          </b-form-group>
            <!-- <b-form-group :label="$t('Phone')" class="has-float-label">
            <b-form-input
              type="text"
              v-model.trim="$v.overLineForm.email.$model"
              :state="!$v.overLineForm.email.$error"
            />
            <b-form-invalid-feedback v-if="!$v.overLineForm.email.required">Email is required!</b-form-invalid-feedback>
            <b-form-invalid-feedback v-else-if="!$v.overLineForm.email.email">Invalid email address</b-form-invalid-feedback>
          </b-form-group> -->
          <b-form-group label="Change Password" class="has-float-label">
            <b-form-input
              type="password"
              v-model.trim="$v.overLineForm.password.$model"
              :state="!$v.overLineForm.password.$error"
            />
            <b-form-invalid-feedback v-if="!$v.overLineForm.password.required">Password is required!</b-form-invalid-feedback>
            <b-form-invalid-feedback v-else-if="!$v.overLineForm.password.minLength">Minimum 6</b-form-invalid-feedback>
            <b-form-invalid-feedback v-else-if="!$v.overLineForm.password.maxLength">Maximum 16</b-form-invalid-feedback>
          </b-form-group>
          <!-- <div class="form-group has-float-label">
            <input-tag v-model="$v.overLineForm.tags.$model"></input-tag>
            <span>{{ $t('forms.tags') }}</span>
            <div
              :class="{'invalid-feedback':true ,'d-block':$v.overLineForm.tags.$error && !$v.overLineForm.tags.required}"
            >At least one tag is required</div>
            <div
              :class="{'invalid-feedback':true ,'d-block':$v.overLineForm.tags.$error && !$v.overLineForm.tags.minLength}"
            >Pick at least 3 tags</div>
          </div> -->
          <!-- <div class="form-group has-float-label">
            <datepicker
              :bootstrap-styling="true"
              :placeholder="$t('form-components.date')"
              v-model="$v.overLineForm.date.$model"
            ></datepicker>
            <span>{{ $t('forms.date') }}</span>
            <div
              :class="{'invalid-feedback':true ,'d-block':$v.overLineForm.date.$error && !$v.overLineForm.date.required}"
            >Date required</div>
          </div> -->
          <!-- <div class="form-group has-float-label">
            <v-select v-model="$v.overLineForm.state.$model" :options="selectData" />
            <span>{{ $t('forms.state') }}</span>
            <div
              :class="{'invalid-feedback':true ,'d-block':$v.overLineForm.state.$error && !$v.overLineForm.state.required}"
            >State is required!</div>
          </div> -->
          <b-button type="submit" variant="primary" class="mt-4">{{ $t('Save')}}</b-button>
        </b-form>
      </b-card>

    </b-colxx>
  </b-row>
                    </b-colxx>
          </b-row>
        </b-container>
      </div>
    </home-layout>
  </div>
</template>

<script>
import InputTag from "../../../components/Form/InputTag";
import vSelect from "vue-select";
import "vue-select/dist/vue-select.css";
import Datepicker from "vuejs-datepicker";

import { validationMixin } from "vuelidate";
const {
  required,
  email,
  minLength,
  maxLength,
  helpers
} = require("vuelidate/lib/validators");

export default {
  components: {
    "input-tag": InputTag,
    "v-select": vSelect,
    "datepicker": Datepicker
  },
  data() {
    return {
      selectData: [
        {
          label: "Chocolate",
          value: "chocolate"
        },
        {
          label: "Vanilla",
          value: "vanilla"
        },
        {
          label: "Strawberry",
          value: "strawberry"
        },
        {
          label: "Caramel",
          value: "caramel"
        },
        {
          label: "Cookies and Cream",
          value: "cookiescream"
        },
        {
          label: "Peppermint",
          value: "peppermint"
        }
      ],
      overLineForm: {
        email: "",
        password: "",
        state: "",
        tags: [],
        date: null
      },
      labelsInInput: {
        email: "",
        password: "",
        state: "",
        tags: [],
        date: null
      }
    };
  },
  mixins: [validationMixin],
  validations: {
    overLineForm: {
      email: {
        required,
        email
      },
      password: {
        required,
        maxLength: maxLength(16),
        minLength: minLength(6)
      },
      state: {
        required
      },
      tags: {
        required,
        minLength: minLength(3)
      },
      date: {
        required
      }
    },
    labelsInInput: {
      email: {
        required,
        email
      },
      password: {
        required,
        maxLength: maxLength(16),
        minLength: minLength(6)
      },
      state: {
        required
      },
      tags: {
        required,
        minLength: minLength(3)
      },
      date: {
        required
      }
    }
  },
  methods: {
    onValitadeOverLineFormFormSubmit() {
      this.$v.overLineForm.$touch();
      console.log("overLineForm is invalid :", this.$v.overLineForm.$invalid);
    },
    onValitadeLabelInInputFormFormSubmit() {
      this.$v.labelsInInput.$touch();
      console.log("labelsInInput is invalid :", this.$v.labelsInInput.$invalid);
    }
  }
};
</script>


<style>
</style>

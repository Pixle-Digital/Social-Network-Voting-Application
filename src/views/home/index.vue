<template>
  <div class="main-container">
    <home-layout>
      <!-- Navbar -->
      <b-navbar toggleable="lg" type="dark">
        <b-container>
          <b-navbar-brand href="#"></b-navbar-brand>

          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav> </b-navbar-nav>

            <!-- Right aligned nav items -->
            <b-navbar-nav
              class="ml-auto d-flex justify-content-center align-items-center"
            >
              <div class="d-none d-md-inline-block align-middle mr-3">
                <button @click="toggleTheme()" class="theme">
                </button>
                                  <Moon height="20px" />

                <switches
                  id="tool-mode-switch"
                  theme="custom"
                  v-model="isDarkActive"
                  class="vue-switcher-small"
                  color="primary"
                />
                <b-tooltip
                  target="tool-mode-switch"
                  placement="left"
                  title="Dark Mode"
                ></b-tooltip>
              </div>
              <b-button v-b-modal.startModal variant="outline-primary"
                >Login</b-button
              >
              <b-button v-b-modal.register variant="primary" class="ml-3"
                >Register</b-button
              >
              <!-- <b-button class="custom-btn-1" to="user/register"
                >Register</b-button
              > -->
            </b-navbar-nav>
          </b-collapse>
        </b-container>
      </b-navbar>

      <div class="row" style="background-color: ">
        <b-container class="bv-example-row">
          <b-row class="mt-5">
            <b-card
              style="
                border-radius: 10px 10px 0 0;
                width: 100%;
                border-bottom: 1px solid #0d3678;
              "
            >
              <b-tabs
                nav-class="separator-tabs ml-0 mb-5"
                content-class="tab-content"
                :no-fade="true"
              >
                <b-tab title="New">
                  <b-row> </b-row>
                </b-tab>
                <b-tab title="Most Viewed">
                  <b-row>
                    <b-colxx> </b-colxx>
                  </b-row>
                </b-tab>
              </b-tabs>
            </b-card>
          </b-row>
          <b-row style="background-color: ">
            <b-container>
              <b-card style="width: 100%" class="mt-4">
                <b-row>
                  <b-col lg="10" sm="6" class="main">
                    <div class="textCountContianer">
                      <div class="count">Character Limit 420</div>
                      <b-form-textarea
                        id="textarea"
                        v-model="textarea"
                        placeholder="Relabel - What's on your mind?"
                        rows="3"
                        maxlength="420"
                        max-rows="6"
                      ></b-form-textarea>
                      <!-- <textarea class='form-control' type="text" maxlength="250"></textarea> -->
                    </div>
                  </b-col>
                  <b-col lg="2" sm="6">
                    <b-button
                      v-b-modal.startModal
                      style="
                        width: 100%;
                        border-radius: 10px;
                        <!-- background-image: linear-gradient(
                          to right,
                          #ae4bfd,
                          #d47cea
                        ); -->
                        border-color: transparent;
                      "
                      >SUBMIT</b-button
                    >
                    <br />
                    <!-- <b-button
                      class="mt-2"
                      v-b-modal.startModal
                      style="
                        width: 100%;
                        border-radius: 10px;
                        background-image: linear-gradient(
                          to right,
                          #ff6aa0,
                          #ff8e70
                        );
                        border-color: transparent;
                      "
                      >SUBMIT ANONYMOUSLY</b-button
                    > -->
                  </b-col>
                </b-row>
              </b-card>
            </b-container>
          </b-row>

          <!-- ---------------posts starts--------------- -->

          <b-row style="background-color: #">
            <b-col class="col-md-3">
              <b-card
                class="mt-4 d-flex flex-row"
                no-body
                id="abc"
                style="
                  width: 100%;
                  padding: 0 !important;
                  border-radius: 10px 10px 0 0;
                "
              >
              </b-card>
            </b-col>
            <b-col class="col-md-9">
              <b-container>
                <b-card
                  class="mt-4 d-flex flex-row"
                  no-body
                  id="abc"
                  style="
                    width: 100%;
                    padding: 0 !important;
                    border-radius: 10px 10px 0 0;
                    border-bottom: 1px solid lightgray;
                  "
                >
                  <router-link to="?" class="d-flex">
                    <img
                      src="/assets/img/profiles/l-1.jpg"
                      alt="Card image cap"
                      class="
                        img-thumbnail
                        list-thumbnail
                        rounded-circle
                        align-self-center
                        m-4
                        small
                      "
                    />
                  </router-link>
                  <div class="d-flex flex-grow-1 min-width-zero">
                    <div
                      class="
                        pl-0
                        align-self-center
                        d-flex
                        flex-column flex-lg-row
                        justify-content-between
                        min-width-zero
                      "
                    >
                      <div class="min-width-zero">
                        <b-row class="mt-2 ml-0">
                          <router-link
                            to="?"
                            style="
                              border-right: 1px solid gray;
                              padding-right: 15px;
                              font-size: 20px;
                              margin-left: -10px;
                            "
                          >
                            <h3 class="mb-1 card-subtitle truncate">
                              Sarah Kortney
                            </h3>
                          </router-link>

                          <span
                            class="ml-3"
                            style="font-size: 18px; color: lightgray"
                            >7 hours</span
                          >
                        </b-row>

                        <b-avatar-group size="20px" class="">
                          <b-avatar></b-avatar>
                          <b-avatar text="BV" variant="primary"></b-avatar>
                          <b-avatar
                            src="https://placekitten.com/300/300"
                            variant="info"
                          ></b-avatar>
                          <b-avatar text="OK" variant="danger"></b-avatar>
                          <b-avatar variant="warning"></b-avatar>
                          <b-avatar
                            src="https://placekitten.com/320/320"
                            variant="dark"
                          ></b-avatar>
                          <b-avatar
                            icon="music-note"
                            variant="success"
                          ></b-avatar>
                        </b-avatar-group>
                        <b-row class="mt-2 ml-0">
                          <span> <strong> Category:</strong></span>

                          <b-badge class="ml-2" pill variant="light"
                            >Secondary</b-badge
                          >
                        </b-row>
                        <!-- <p class="text-muted text-small mb-2">Executive Director</p> -->
                      </div>
                    </div>
                  </div>
                  <!-- <b-card class="mb-4 d-flex flex-row" no-body>

          </b-card> -->
                  <!-- <b-list-group-item
                  class="align-items-center"
                  style="border: none; padding: 0"
                >
                  <b-avatar
                    variant="info"
                    src="https://placekitten.com/300/300"
                    class="mr-3"
                  ></b-avatar>
                  <span
                    class="mr-auto"
                    style="
                      border-right: 1px solid gray;
                      padding-right: 15px;
                      font-size: 20px;
                      margin-left: -10px;
                    "
                    >Super Kitty</span
                  >

                  <span
                    class="mr-auto ml-2"
                    style="font-size: 18px; color: lightgray"
                    >7 hours</span
                  >
                  <b-avatar-group size="20px" class="ml-5">
                    <b-avatar></b-avatar>
                    <b-avatar text="BV" variant="primary"></b-avatar>
                    <b-avatar
                      src="https://placekitten.com/300/300"
                      variant="info"
                    ></b-avatar>
                    <b-avatar text="OK" variant="danger"></b-avatar>
                    <b-avatar variant="warning"></b-avatar>
                    <b-avatar
                      src="https://placekitten.com/320/320"
                      variant="dark"
                    ></b-avatar>
                    <b-avatar icon="music-note" variant="success"></b-avatar>
                  </b-avatar-group>
                  <b-row class="mt-3 ml-3">
                    <span>Category:</span>

                    <b-badge class="ml-2" pill variant="light"
                      >Secondary</b-badge
                    >
                  </b-row>
                </b-list-group-item> -->
                </b-card>
                <!-- <b-card
                id="abc"
                style="
                  width: 100%;
                  padding: 0 !important;
                  border-radius: 10px 10px 0 0;
                  border-bottom: 1px solid lightgray;
                "
                class="mt-4"
              >
                <b-list-group-item
                  class="align-items-center"
                  style="border: none; padding: 0"
                >
                  <b-avatar
                    variant="info"
                    src="https://placekitten.com/300/300"
                    class="mr-3"
                  ></b-avatar>
                  <span
                    class="mr-auto"
                    style="
                      border-right: 1px solid gray;
                      padding-right: 15px;
                      font-size: 20px;
                      margin-left: -10px;
                    "
                    >Super Kitty</span
                  >

                  <span
                    class="mr-auto ml-2"
                    style="font-size: 18px; color: lightgray"
                    >7 hours</span
                  >
                  <b-avatar-group size="20px" class="ml-5">
                    <b-avatar></b-avatar>
                    <b-avatar text="BV" variant="primary"></b-avatar>
                    <b-avatar
                      src="https://placekitten.com/300/300"
                      variant="info"
                    ></b-avatar>
                    <b-avatar text="OK" variant="danger"></b-avatar>
                    <b-avatar variant="warning"></b-avatar>
                    <b-avatar
                      src="https://placekitten.com/320/320"
                      variant="dark"
                    ></b-avatar>
                    <b-avatar icon="music-note" variant="success"></b-avatar>
                  </b-avatar-group>
                  <b-row class="mt-3 ml-3">
                    <span>Category:</span>

                    <b-badge class="ml-2" pill variant="light"
                      >Secondary</b-badge
                    >
                  </b-row>
                </b-list-group-item>
              </b-card> -->
                <b-card
                  id="abd"
                  style="border-radius: 0; border-bottom: 1px solid lightgray"
                >
                  <p>
                    But I must explain to you how all this mistaken idea of
                    denouncing pleasure and praising pain was born and I will
                    give you a complete account of the system, and expound the
                    actual teachings of the great explorer of the truth, the
                    master-builder of human happiness. No one rejects, dislikes,
                    or avoids pleasure itself, because it is pleasure, but
                    because those who do not know how to pursue pleasure
                    rationally encounter consequences that are extremely
                    painful. Nor again is there anyone who loves or pursues or
                    desires to obtain pain of itself, because it is pain, but
                    because occasionally circumstances occur in which toil and
                    pain can procure him some great pleasure. To take a
                  </p>
                </b-card>

                <b-card
                  id="abe"
                  style="
                    border-radius: 0;
                    background-color: #;
                    box-shadow: none;
                  "
                >
                  <!-- <b-progress  :value="value" :max="max" class="mt-4 mb-3"></b-progress> -->

                  <b-progress :max="max" height="43px" class="mt-4 mb-3">
                    <b-progress-bar
                      style="
                        background-image: linear-gradient(
                          to right,
                          #d47cea,
                          #ae4bfd
                        );
                        height: 13px;
                        margin-top: 15px;
                      "
                      :value="values[0]"
                    ></b-progress-bar>
                    <!-- <b-card  style="    border-radius: 10px 10px 10px 10px;
    width: 181px;
    height: 31px;
    background-color: aquamarine;
    /* margin: auto; */
    /* position: absolute; */
    margin-top: -8px;
">

                    </b-card> -->
                    <b-button
                      variant="danger"
                      style="
                        background-image: linear-gradient(
                          to right,
                          #ff6aa0,
                          #ae4bfd
                        );
                        border-radius: inherit;
                        font-size: 19px;
                        border: none;
                      "
                      >10:90:50</b-button
                    >
                    <b-progress-bar
                      style="
                        background-image: linear-gradient(
                          to right,
                          #ff6aa0,
                          #ff8e70
                        );
                        height: 13px;
                        margin-top: 15px;
                      "
                      :value="values[1]"
                    ></b-progress-bar>
                  </b-progress>

                  <!-- <div class="progress-bar-container">
                  <div class="progress-bar positive full"></div>
                  <div class="first marker"></div>
                  <div class="middle marker"></div>
                  <div class="last marker"></div>

                  <div class="labels">
                    <div class="left-label">Agree</div>
                    <div class="right-label">Disagree</div>
                  </div>
                </div> -->
                </b-card>

                <b-card id="abf" style="border-radius: 0 0 10px 10px">
                  <b-button-group
                    size="lg"
                    style="width: 100%; margin-bottom: 13px"
                  >
                    <b-button
                      class="hover-switch"
                      variant="none"
                      style="border: none; margin-top: -28px"
                    >
                      <img src="../../assets/img/no.png" alt="" />
                    </b-button>
                    <b-button
                      class="hover-switch"
                      variant="none"
                      style="border: none; margin-top: -28px"
                    >
                      <img src="../../assets/img/next.png" alt="" />
                    </b-button>
                    <b-button
                      class="hover-switch"
                      variant="none"
                      style="border: none; margin-top: -28px"
                    >
                      <img src="../../assets/img/trophy.png" alt="" />
                    </b-button>
                    <b-button
                      class="hover-switch"
                      variant="none"
                      style="border: none; margin-top: -28px"
                    >
                      <img src="../../assets/img/report.png" alt="" />
                    </b-button>
                    <b-button
                      class="hover-switch"
                      variant="none"
                      style="border: none; margin-top: -28px"
                    >
                      <img src="../../assets/img/yes.png" alt="" />
                    </b-button>
                  </b-button-group>
                </b-card>
              </b-container>
            </b-col>
          </b-row>
        </b-container>
      </div>

      <!-- Footer Section -->
      <!-- <div class="section-footer">
        <p class="m-0 p-0">Copyright © 2022 . All rights reserved.</p>

        <div class="footer-breadcrums">
          <b-link class="footer-breadcrums-link">Blog</b-link>
          - <b-link class="footer-breadcrums-link">Success Stories</b-link> -
          <b-link class="footer-breadcrums-link">About Us</b-link> -
          <b-link class="footer-breadcrums-link">Terms</b-link>
          -
          <b-link class="footer-breadcrums-link">Privacy Policy</b-link>
          -
          <b-link class="footer-breadcrums-link">Contact</b-link>
          -
          <b-link class="m-0 p-0" variant="empty">
            <b-img src="/assets/img/login/facebook.png" height="20"></b-img>
          </b-link>
          <b-link class="m-0 p-0" variant="empty">
            <b-img src="/assets/img/login/twitter.png" height="20"></b-img>
          </b-link>
          <b-link class="m-0 p-0" variant="empty">
            <b-img src="/assets/img/login/google.png" height="20"></b-img>
          </b-link>
        </div>
      </div> -->

      <!-- Start Modal -->
      <b-modal id="startModal" title="Login" hide-header centered hide-footer>
        <div>
          <Login />
        </div>
      </b-modal>
      <b-modal id="register" title="Register" hide-header centered hide-footer>
        <div>
          <Register />
        </div>
      </b-modal>
    </home-layout>
  </div>
</template>

<script>
import HomeLayout from "../../layouts/HomeLayout.vue";
import { getThemeColor, setThemeColor } from "../../utils";
import VueScrollTo from "vue-scrollto";
import Login from "../user/Login.vue";
import Register from "../user/Register.vue";
import Switches from "vue-switches";
import IconCard from "../../components/Cards/IconCard";
import Moon from "../../../src/assets/img/moon.svg";


const scrollOptions = {
  container: "body",
  easing: "ease-in",
  offset: -120,
  force: true,
  x: false,
  y: true,
};

export default {
  components: {
    "home-layout": HomeLayout,
    switches: Switches,
    "icon-card": IconCard,
    Login,
    Register,
    Moon
  },
  data() {
    return {
      values: [400, 200],
      max: 50,
      theme: "",
      isDarkActive: false,
      textarea: "",
      form: {
        email: "",
        name: "",
        food: null,
        checked: [],
      },
      selected: null,
      options: [
        { value: null, text: "All" },
        { value: "a", text: "Entertainment" },
        { value: "b", text: "Media" },
      ],

      foods: [
        { text: "Select One", value: null },
        "Carrots",
        "Beans",
        "Tomatoes",
        "Corn",
      ],
      show: true,
    };
  },
  methods: {
    toggleTheme() {
      this.theme = this.theme == "darkMode" ? "" : "darkMode"; //toggles theme value
      document.documentElement.setAttribute("data-theme", this.theme); // sets the data-theme attribute
      localStorage.setItem("theme", this.theme); // stores theme value on local storage
    },

    scrollTo(target) {
      VueScrollTo.scrollTo(target, 200, scrollOptions);
    },
  },
  mounted() {
    let localTheme = localStorage.getItem("theme"); //gets stored theme value if any
    document.documentElement.setAttribute("data-theme", localTheme); // updates the data-theme attribute
  },
  created() {
    const color = getThemeColor();
    this.isDarkActive = color.indexOf("dark") > -1;
  },
  watch: {
    // "$i18n.locale"(to, from) {
    //   if (from !== to) {
    //     this.$router.go(this.$route.path);
    //   }
    // },
    isDarkActive(val) {
      let color = getThemeColor();
      let isChange = false;
      if (val && color.indexOf("light") > -1) {
        isChange = true;
        color = color.replace("light", "dark");
      } else if (!val && color.indexOf("dark") > -1) {
        isChange = true;
        color = color.replace("dark", "light");
      }
      if (isChange) {
        setThemeColor(color);
        setTimeout(() => {
          window.location.reload();
        }, 500);
      }
    },
  },
  beforeDestroy() {},
};
</script>

<style lang="scss">
$size: 8px;
$progress-width: 100%;
#abc .card-body {
  padding-bottom: 13px;
  padding-top: 13px;
}
#abd .card-body {
  padding-bottom: 13px;
  padding-top: 13px;
}
#abe .card-body {
  padding-bottom: 13px;
  padding-top: 0;
}
#abf .card-body {
}
.section-1 {
  padding: 50px;
  background-image: url("https://onestopdesigning.com/qavah/themes/love/assets/img/banner-01.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
  min-height: 90vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
}

.section-1 .content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.section-1 .content .title {
  font-size: 2rem;
  font-weight: bold;
  color: #93652b;
}

.section-1 .description {
  font-size: 1rem;
  font-weight: bold;
  color: #93652b;
}

.section-2 {
  background-image: url("/assets/img/landing-page/mobiles-screens.png");
  background-size: contain;
  background-repeat: no-repeat;
  /* background-position: center center; */
  height: 400px;
}

.section-3 .items-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.section-3 .items-container .item {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  max-width: 350px;
}

.section-3 .items-container .item .title {
  font-size: 1.5rem;
}

.section-4 {
  padding: 2rem 0;
  /* display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center; */
}

.section-4 .heading {
  display: flex;
  justify-content: center;
  align-items: center;
}

.section-4 .get-started-btn {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 1rem;
}

.section-4 .left {
  display: flex;
  justify-content: center;
  align-items: center;
}

.section-4 .right {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1rem;
}

.section-4 .right .title {
  font-size: 1.2rem;
  color: #93652b;
}

.custom-btn-1 {
  background-color: #93652b !important;
  outline: none;
  border: none;
  border-radius: 10px;
  color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1rem 2rem;
}

.section-footer {
  margin-top: 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 2rem;
}

// .progress-bar-container {
//   width: $progress-width;
//   height: $size/4;
//   background: #ddd;
//   position: relative;
//   margin: $size * 4 $size * 2;

//   .progress-bar {
//     height: 5px;
//     margin-top: -1px;
//     position: absolute;
//     z-index: 1;
//     border-radius: $size/4;

//     &.positive {
//       background: #0aa96c;
//       margin-left: $progress-width/2;
//     }

//     &.neutral {
//       background: #666;
//       margin-left: calc(#{$progress-width/2} - #{$progress-width/8});

//       & ~ .middle {
//         z-index: 0;
//       }
//     }

//     &.negative {
//       background: #ce1d19;

//       &.half {
//         margin-left: $progress-width/4;
//       }
//     }

//     &.full {
//       width: $progress-width/2;
//     }

//     &.half {
//       width: $progress-width/4;
//     }
//   }

//   .marker {
//     position: absolute;
//     top: -$size/4;
//     width: $size/4;
//     height: $size * 0.75;
//     background: #ddd;
//     z-index: 2;

//     &.first {
//       left: 0;
//     }

//     &.middle {
//       left: calc(50% - 1px);
//     }

//     &.last {
//       right: 0;
//     }
//   }
// }

.labels {
  width: $progress-width;
  margin-top: $size * 1.5;
  font-size: 11px;
  display: flex;
  justify-content: space-between;
  font-family: sans-serif;

  .left-label {
  }

  .right-label {
    text-align: right;
  }
}

.hover-switch > img {
  position: absolute;
}
/*
 * Show the last image by default
*/
.hover-switch > img:last-of-type {
  width: 30px;
  transition: width 0.5s ease-in-out;
  -moz-transition: width opacity 0.5s ease-in-out;
  -webkit-transition: width opacity 0.5s ease-in-out;
}
/*
 * Hide the last image on hover
*/
.hover-switch:hover > img:last-of-type {
  width: 50px;
}

.count {
  position: absolute;
  bottom: 1px;
  right: 21px;
  color: gray;
  font-size: 11px;
}
.textCountContianer {
  position: relative;
}
</style>




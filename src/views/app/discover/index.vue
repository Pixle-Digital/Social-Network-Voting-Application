<template>
  <div class="">
    <home-layout>
      <!-- Navbar -->

      <div class="row">
        <b-container class="bv-example-row">
          <b-row class="">
            <b-col md="3">
              <b-card class="d-flex flex-row" no-body id="abc">
                <b-nav vertical class="w-25">
                  <b-nav-item active>active</b-nav-item>
                  <b-nav-item>link</b-nav-item>
                  <b-nav-item>adawda</b-nav-item>
                </b-nav>
              </b-card>
            </b-col>
            <b-col md="9">
              <b-card class="d-flex flex-row">
                <b-nav>
                  <b-nav-item>Sort By:</b-nav-item>
                  <b-nav-item active>New</b-nav-item>
                  <b-nav-item>Most Voted</b-nav-item>
                  <b-nav-item>Not Voted</b-nav-item>
                  <b-nav-item>Hot</b-nav-item>
                  <b-nav-item>Archive</b-nav-item>
                  <b-nav-item>Notifications</b-nav-item>
                </b-nav>
              </b-card>
            </b-col>
          </b-row>
          <b-row style="background-color: ">
            <b-col md="9" offset-md="3">
                <b-card style="width: 100%" >
                  <b-form
                    @submit.prevent="formSubmit"
                    class="mt-4 av-tooltip tooltip-label-bottom"
                  >
                    <b-row>
                      <b-col lg="10" sm="6">


                        <!-- Text Area of Post -->
                        <b-form-group>
                                                  <div class="textCountContianer">

                          <div class="count">Character Limit 420</div>
                          <b-form-textarea
                            id="textarea"
                            type="text"
                            class="custom-field"
                            placeholder="Relabel - What's on your mind?"
                            rows="3"
                            maxlength="420"
                            max-rows="6"
                            v-model="$v.form.post.$model"
                            :state="!$v.form.post.$error"
                          />
                                                  </div>

                          <b-form-invalid-feedback
                            v-if="!$v.form.post.required"
                          >
                            Please Write Something</b-form-invalid-feedback
                          >

                          <b-form-invalid-feedback
                            v-else-if="!$v.form.post.maxLength"
                            >Your Post must be maximum 420
                            characters</b-form-invalid-feedback
                          >
                        </b-form-group>
                        <!-- <b-form-group>
                        <v-select
                          type="select"
                          placeholder="Select Category"
                          v-model="$v.form.cat.$model"
                          :state="!$v.form.cat.$error"
                          :options="selectData"
                        />
                      </b-form-group> -->
                      </b-col>
                      <b-col lg="2" sm="6">
                        <b-button
                          type="submit"
                          block
                          variant="danger"
                          :disabled="processing"
                          :class="{
                            'btn-multiple-state btn-shadow': true,
                            'show-spinner': processing,
                            'show-success': !processing && loginError === false,
                            'show-fail': !processing && loginError,
                          }"
                          style="
                            width: 100%;
                            border-radius: 10px;
                            background-image: linear-gradient(
                              to right,
                              #ae4bfd,
                              #d47cea
                            );
                            border-color: transparent;
                          "
                        >
                          <span class="spinner d-inline-block">
                            <span class="bounce1"></span>
                            <span class="bounce2"></span>
                            <span class="bounce3"></span>
                          </span>
                          <span class="icon success">
                            <i class="simple-icon-check"></i>
                          </span>
                          <span class="icon fail">
                            <i class="simple-icon-exclamation"></i>
                          </span>
                          <span class="label">SUBMIT </span>
                        </b-button>
                        <br />
                        <!-- <b-button
                        class="mt-2"
                        style="
                          width: 100%;
                          border-radius: 10px;
                          background-image: linear-gradient(to right,#ff6aa0,#ff8e70);
                          border-color: transparent;
                        "
                        >SUBMIT ANONYMOUSLY</b-button
                      > -->
                      </b-col>
                    </b-row>
                  </b-form>
                </b-card>
            </b-col>
          </b-row>

          <!-- ---------------posts starts--------------- -->

          <b-row>
            <b-col offset-md="3" class="col-md-9">
              <b-container
                v-for="item in postsd.slice().reverse()"
                :key="item.text"
              >
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
                              {{ item.username }} <br>

                            </h3>
                            <p class="text-muted text-small mb-2">@{{item.username}}</p>
                          </router-link>

                          <span
                            class="ml-3"
                            style="font-size: 18px; color: lightgray"
                            >{{ item.createdAt }}</span
                          >
                        </b-row>

                        <b-row class="mt-2 ml-0">
                          <span> <strong> Followers:</strong></span>

                          <b-badge class="ml-2" pill variant="outline-secondary">34</b-badge>
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
                  <p class="text-medium" style="font-size: 1.85rem;
    line-height: 2.3rem;">
                    {{ item.text }}
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
                <div class="hourglass"></div>

                  <!-- <b-progress  :value="value" :max="max" class="mt-4 mb-3"></b-progress> -->

                  <!-- <b-progress :max="max" height="43px" class="mt-4 mb-3">
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
                    ></b-progress-bar> -->
                    <!-- <b-card  style="    border-radius: 10px 10px 10px 10px;
    width: 181px;
    height: 31px;
    background-color: aquamarine;
    /* margin: auto; */
    /* position: absolute; */
    margin-top: -8px;
">

                    </b-card> -->
                    <!-- <b-button
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
                      >{{ item.expiry }}
                    </b-button>
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
                  </b-progress> -->

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
                      v-on:click="agreebtn()"
                    >
                      <img src="../../../assets/img/no.png" alt="" />
                    </b-button>
                    <b-button
                      class="hover-switch"
                      variant="none"
                      style="border: none; margin-top: -28px"
                    >
                      <img src="../../../assets/img/next.png" alt="" />
                    </b-button>
                    <b-button
                      class="hover-switch"
                      variant="none"
                      style="border: none; margin-top: -28px"
                    >
                      <img src="../../../assets/img/trophy.png" alt="" />
                    </b-button>
                    <b-button
                      class="hover-switch"
                      variant="none"
                      style="border: none; margin-top: -28px"
                      v-on:click="reportbtn()"
                    >
                      <img src="../../../assets/img/report.png" alt="" />
                    </b-button>
                    <b-button
                      class="hover-switch"
                      variant="none"
                      style="border: none; margin-top: -28px"
                      v-on:click="disagreebtn()"
                    >
                      <img src="../../../assets/img/yes.png" alt="" />
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
import HomeLayout from "../../../layouts/HomeLayout.vue";
import VueScrollTo from "vue-scrollto";
import Login from "../../user/Login.vue";
import Register from "../../user/Register.vue";
import IconCard from "../../../components/Cards/IconCard";
import firebase from "firebase";
import moment from "moment";
import { validationMixin } from "vuelidate";
import { mapGetters, mapActions } from "vuex";
import vSelect from "vue-select";
import "vue-select/dist/vue-select.css";
import _ from "lodash";

const { required, minLength, maxLength , email } = require("vuelidate/lib/validators");

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
    Login,
    Register,
    "icon-card": IconCard,
    "v-select": vSelect,
  },
  data() {
    const db = firebase.database();
    return {
      countDown: 10,
      postssnap: db.ref("posts"),
      usersssnap: db.ref("users"),
      values: [50, 50],
      username: "",
      max: 50,
      posts: {
        data: {},
      },
      user: {
        data: {},
      },
      selectData: [
        "Politics",
        "Entertainment",
        "Philosophy",
        "Finance",
        "General",
      ],
      userdata: [],
      postsd: [],
      theme: "",
      textarea: "",
      form: {
        email: "",
        post: "",
        cat: "",
        name: "",
        food: null,
        checked: [],
      },
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
  watch: {
    "posts.data": {
      handler: function (val) {
        let List = [];
        _.map(val, (post, key) => {
          List.push({
            key: key,
            createdAt: moment(post.createdAt).startOf("hour").fromNow(), // 15 hours ago
            text: post.text,
            category: post.category,
            username: `${
              this.user.data[post.uid]
                ? this.user.data[post.uid].username
                : "username"
            }`,
            expiry: moment(post.expiry).format("LTS"), // 2:47:15 PM
          });
        });
        this.postsd = List;
      },
      deep: true,
    },
    // "user.data": {
    //   handler: function (val) {
    //     let self = this;
    //     let List = [];
    //     _.map(val, (user, key) => {
    //       List.push({
    //         key: key,
    //         createdAt: moment(user.createdAt).startOf("hour").fromNow(), // 15 hours ago
    //         email: user.text,
    //         username: user.username,
    //       });
    //     });
    //     this.username = List;
    //   },
    //   deep: true,
    // },
    loginError(val) {
      if (val != null) {
        this.$notify("error", "Login Error", val, {
          duration: 3000,
          permanent: false,
        });
      }
    },
    currentUser(val) {
      if (val && val.uid && val.uid.length > 0) {
        setTimeout(() => {
          this.$router.push(adminRoot);
        }, 200);
      }
    },
  },
  computed: {
    ...mapGetters(["currentUser", "processing", "loginError"]),
  },
  mixins: [validationMixin],
  validations: {
    form: {
      post: {
        required,
        maxLength: maxLength(420),
      },
      email: {
        required,
        email,
        minLength: minLength(4),
      },
      cat: {
        required,
      },
    },
  },
  methods: {
    countDownTimer() {
      if (this.countDown > 0) {
        setTimeout(() => {
          this.countDown -= 1;
          this.countDownTimer();
        }, 1000);
      }
    },
    loadposts() {
      let self = this;
      self.postssnap.once("value").then((snap) => {
        console.log(snap.val());
        // this.postsd = snap.val()
      });
    },
    agreebtn() {
      swal({
        title: "Are you sure?",
        text: "do you agree with this Question",
        icon: "warning",
        buttons: true,
        dangerMode: true,
      }).then((willDelete) => {
        if (willDelete) {
          swal("Poof! Your Vote Submitted Successfully !", {
            icon: "success",
          });
        } else {
          swal("Read agian!");
        }
      });
    },
    disagreebtn() {
      swal({
        title: "Are you sure?",
        text: "do you Dis-agree with this Question",
        icon: "warning",
        buttons: true,
        dangerMode: true,
      }).then((willDelete) => {
        if (willDelete) {
          swal("Poof! Your Vote Submitted Successfully !", {
            icon: "success",
          });
        } else {
          swal("Read agian!");
        }
      });
    },
    reportbtn() {
      swal({
        title: "Are you sure?",
        text: "do you want to report this Question",
        icon: "warning",
        buttons: true,
        dangerMode: true,
      }).then((willDelete) => {
        if (willDelete) {
          swal("Poof! Submitted Successfully !", {
            icon: "success",
          });
        } else {
          swal("Not Submitted!");
        }
      });
    },
    formSubmit() {
      if (this.form.post != "" ) {
        let self = this;
        self.postssnap
          .push({
            createdAt: moment().valueOf(),
            text: this.form.post,
            agree: 2,
            disagree: 4,
            expiry: moment().valueOf(),
            report: 4,
            awards: 4,
            uid: this.currentUser.uid,
          })
          .then((data) => {
            swal({
              title: "Post Created Successfully !",
              text: ``,
              icon: "success",
            });
          })
          .catch((err) => {
            this.error = err.message;
          });
      } else {
        this.$bvToast.toast(`Post is empty `, {
          title: `Please Fill the field `,
          autoHideDelay: 5000,
          variant: "danger",
          solid: true,
        });
      }
    },
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
    this.countDownTimer();
    this.usersssnap
      .orderByChild("uid")
      .equalTo(this.currentUser.uid)
      .on(
        "value",
        (snap) => ((this.user.data = snap.val()), console.log(this.user.data))
      );

    // this.postssnap.orderByChild('uid').equalTo(this.currentUser.uid).on("value",snap =>
    // (
    //   this.user.data = snap.val(),
    //   console.log(this.user.data)
    // ));

    this.postssnap.on("value", (dataSnapshot) => {
      this.posts.data = dataSnapshot.val();
    });
    this.loadposts();
    console.log(this.currentUser.uid);
    let localTheme = localStorage.getItem("theme"); //gets stored theme value if any
    document.documentElement.setAttribute("data-theme", localTheme); // updates the data-theme attribute
  },
  beforeDestroy() {},
};
</script>

<style scoped>
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

.hourglass {
 --bg: #e3e4e8;
 --fg: #2e3138;
 --primary: #00ba34;
 font-size: calc(5px + (24 - 16) * (100vw - 320px) / (1280 - 320));
}


.hourglass,
.hourglass:before,
.hourglass:after {
 animation-duration: 10s;
 animation-iteration-count: infinite;
}
.hourglass {
 --polygonH: polygon(
  0% 0%,
  100% 0%,
  100% 5.55%,
  95% 5.55%,
  95% 28%,
  60% 46%,
  60% 54%,
  95% 72%,
  95% 94.45%,
  100% 94.45%,
  100% 100%,
  0% 100%,
  0% 94.45%,
  5% 94.45%,
  5% 72%,
  40% 54%,
  40% 46%,
  5% 28%,
  5% 5.55%,
  0% 5.55%
 );
 animation-name: flip;
 animation-timing-function: ease-in-out;
 background-image: linear-gradient(
  var(--primary) 0.5em,
  #737a8c55 0.5em 8.5em,
  var(--primary) 8.5em
 );
 clip-path: var(--polygonH);
 -webkit-clip-path: var(--polygonH);
 overflow: hidden;
 position: relative;
 width: 5em;
 height: 9em;
 z-index: 0;
}
.hourglass:before,
.hourglass:after {
 animation-timing-function: linear;
 content: "";
 display: block;
 position: absolute;
}
.hourglass:before {
 --polygonB1: polygon(
  0% 0%,
  100% 0%,
  100% 24%,
  50% 47%,
  50% 47%,
  50% 47%,
  50% 47%,
  50% 47%,
  50% 47%,
  50% 47%,
  50% 47%,
  0% 24%
 );
 --polygonB2: polygon(
  0% 4%,
  100% 4%,
  100% 24%,
  55% 45%,
  55% 100%,
  55% 100%,
  55% 100%,
  45% 100%,
  45% 100%,
  45% 100%,
  45% 45%,
  0% 24%
 );
 --polygonB3: polygon(
  0% 24%,
  100% 24%,
  100% 24%,
  55% 45%,
  55% 80%,
  100% 100%,
  100% 100%,
  0% 100%,
  0% 100%,
  45% 80%,
  45% 45%,
  0% 24%
 );
 --polygonB4: polygon(
  45% 45%,
  55% 45%,
  55% 45%,
  55% 45%,
  55% 58%,
  100% 76%,
  100% 100%,
  0% 100%,
  0% 76%,
  45% 58%,
  45% 45%,
  45% 45%
 );
 --polygonB5: polygon(
  50% 53%,
  50% 53%,
  50% 53%,
  50% 53%,
  50% 53%,
  100% 76%,
  100% 100%,
  0% 100%,
  0% 76%,
  50% 53%,
  50% 53%,
  50% 53%
 );
 animation-name: fill;
 background-color: var(--fg);
 background-size: 100% 3.6em;
 clip-path: var(--polygonB1);
 -webkit-clip-path: var(--polygonB1);
 top: 0.5em;
 left: 0.5em;
 width: 4em;
 height: 8em;
 z-index: 1;
}
.hourglass:after {
 animation-name: glare;
 background: linear-gradient(
    90deg,
    #0000 0.5em,
    #0003 0.5em 1.5em,
    #0000 1.5em 3.5em,
    #fff3 3.5em 4.5em,
    #fff0 4.5em 6.5em,
    #0003 6.5em 7.5em,
    #0000 7.5em
   )
   0 0 / 100% 0.5em,
  linear-gradient(
    90deg,
    #0000 0.75em,
    #0003 0.75em 1.25em,
    #0000 1.25em 3.75em,
    #fff3 3.75em 4.25em,
    #fff0 4.25em 6.75em,
    #0003 6.75em 7.25em,
    #0000 7.25em
   )
   0 0.5em / 100% 8em,
  linear-gradient(
    90deg,
    #0000 0.5em,
    #0003 0.5em 1.5em,
    #0000 1.5em 3.5em,
    #fff3 3.5em 4.5em,
    #fff0 4.5em 6.5em,
    #0003 6.5em 7.5em,
    #0000 7.5em
   )
   0 100% / 100% 0.5em;
 background-repeat: repeat-x;
 top: 0;
 left: -3em;
 width: 200%;
 height: 100%;
 z-index: 2;
}
/* Animations */
@keyframes fill {
 from {
  clip-path: var(--polygonB1);
  -webkit-clip-path: var(--polygonB1);
 }
 10% {
  clip-path: var(--polygonB2);
  -webkit-clip-path: var(--polygonB2);
 }
 45% {
  clip-path: var(--polygonB3);
  -webkit-clip-path: var(--polygonB3);
 }
 80% {
  clip-path: var(--polygonB4);
  -webkit-clip-path: var(--polygonB4);
 }
 85%,
 to {
  clip-path: var(--polygonB5);
  -webkit-clip-path: var(--polygonB5);
 }
}
@keyframes glare {
 from,
 90% {
  transform: translateX(0);
 }
 to {
  transform: translateX(3em);
 }
}
@keyframes flip {
 from,
 90% {
  transform: rotate(0);
 }
 to {
  transform: rotate(180deg);
 }
}
@media (prefers-color-scheme: dark) {
 .hourglass {
  --bg: #050505;
  --fg: #00ba34;
 }
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




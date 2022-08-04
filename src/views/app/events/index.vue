<template>
  <div class="">
    <home-layout>
      <!-- Navbar -->

  <b-row class="">
            <b-card
              style="
                border-radius: 10px 10px 10px 10px;
                width: 100%;
              "
            >
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
        <button type="button" class="btn btn-default"  >
          <router-link to="preferences">
Preferences
          </router-link>

</button>
    </b-card>
    </b-col>
    <b-col cols="2">
       <b-card>
<button type="button" class="btn btn-default" aria-label="Left Align">
   <router-link to="settings">
Settings
          </router-link>

</button>
      </b-card>
      </b-col>
      <b-col cols="2">
       <b-card>
<button type="button" class="btn btn-default" aria-label="Left Align">
   <router-link to="awards">
Awards
          </router-link>

</button>
      </b-card>
      </b-col>
  </b-row>
            </b-card>
          </b-row>
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
              <b-nav>
                <b-nav-item>Sort By:</b-nav-item>
                <b-nav-item active>Date</b-nav-item>
                <b-nav-item>Voted</b-nav-item>
                <b-nav-item>Category</b-nav-item>
              </b-nav>
            </b-card>
          </b-row>


          <!-- ---------------posts starts--------------- -->

   <b-row style="background-color: #" v-for="item in postsd.slice().reverse()"
            :key="item.text">
            <b-container>
              <b-card class=" mt-4 d-flex flex-row" no-body
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
                class="img-thumbnail list-thumbnail rounded-circle align-self-center m-4 small"
              />
            </router-link>
            <div class="d-flex flex-grow-1 min-width-zero">
              <div
                class="pl-0 align-self-center d-flex flex-column flex-lg-row justify-content-between min-width-zero"
              >
                <div class="min-width-zero">
                  <b-row class="mt-2 ml-0">
                   <router-link to="?" style=" border-right: 1px solid gray;
                      padding-right: 15px;
                      font-size: 20px;
                      margin-left: -10px;">
                    <h3 class="mb-1 card-subtitle truncate">Sarah Kortney</h3>

                  </router-link>

                   <span
                    class=" ml-3"
                    style="font-size: 18px; color: lightgray"
                    >{{item.createdAt}}</span
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
                    <b-avatar icon="music-note" variant="success"></b-avatar>
                  </b-avatar-group>
                  <b-row class="mt-2 ml-0">
                    <span> <strong> Category:</strong></span>

                    <b-badge class="ml-2" pill variant="light"
                      >{{item.category}}</b-badge
                    >
                  </b-row>
                  <!-- <p class="text-muted text-small mb-2">Executive Director</p> -->
                </div>
              </div>
            </div>

              </b-card>

              <b-card id="abd" style="border-radius: 0; border-bottom: 1px solid lightgray;">
                <p>
                  {{item.text}}
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
      <b-progress-bar  style="background-image: linear-gradient(to right,#d47cea,#ae4bfd);height:13px;margin-top: 15px;" :value="values[0] + item.agree"></b-progress-bar>
                                       <b-button variant="danger" style="background-image: linear-gradient(to right,#ff6aa0,#ae4bfd);
                    border-radius:inherit;font-size: 19px;border: none;">-</b-button>
      <b-progress-bar style="background-image: linear-gradient(to right,#ff6aa0,#ff8e70);height:13px;margin-top: 15px;" :value="values[1] + item.disagree"></b-progress-bar>
    </b-progress>




              </b-card>

              <b-card id="abf" style="border-radius: 0 0 10px 10px">

                <b-button-group size="lg" style="width: 100%; margin-bottom: 13px;">
                  <b-button class="hover-switch" variant="none"
                    style="border: none; margin-top:-28px"
                  >
                  <center>
<img src="../../../assets/img/no.png" alt=""  />
                    <br>
                    {{item.agree}} Agree
                  </center>


                  </b-button>
                  <b-button class="hover-switch" variant="none"
                    style="border: none; margin-top:-28px"
                  >
                  <center>
<img src="../../../assets/img/yes.png" alt="" />
                    <br>
                    {{item.disagree}} Disagree
                  </center>

                  </b-button>
                </b-button-group>
              </b-card>
            </b-container>
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

const { required, minLength, email } = require("vuelidate/lib/validators");

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
      countDown : 10,
      postssnap: db.ref("posts"),
      usersssnap: db.ref("users"),
      values: [50, 50],
      username: "",
      max: 50,
      posts: {
        data: {},
      },
      user:{
        data:{}
      },
      selectData: [
        "Politics",
        "Entertainment",
        "Philosophy",
        "Finance",
        "General",
      ],
      userdata:[],
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
            username: `${this.user.data[post.uid] ? this.user.data[post.uid].username : "username"}`,
            expiry: moment(post.expiry).format("LTS"), // 2:47:15 PM
            agree: post.agree,
            disagree: post.disagree
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
        minLength: minLength(4),
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
      if(this.countDown > 0) {
          setTimeout(() => {
              this.countDown -= 1
              this.countDownTimer()
        }, 1000)
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
      if (this.form.post != "" && this.form.cat != "") {
        let self = this;
        self.postssnap
          .push({
            createdAt: moment().valueOf(),
            text: this.form.post,
            category: this.form.cat,
            agree: 2,
            disagree: 4,
            expiry: moment().valueOf(),
            report: 4,
            awards: 4,
            uid: this.currentUser.uid
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
    this.countDownTimer()
    this.usersssnap.orderByChild('uid').equalTo(this.currentUser.uid).on("value",snap =>
    (
      this.user.data = snap.val(),
      console.log(this.user.data)
    ));

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
</style>




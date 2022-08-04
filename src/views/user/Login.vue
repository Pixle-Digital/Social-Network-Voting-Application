<template>
<b-container>
    <b-row>
    <b-col lg="12" md="12" sm="12">
      <div class="h-100 form-side mt-5">
        <!-- <router-link tag="a" to="/">
          <span class="logo-single" />
        </router-link> -->

        <div>
          <p class="title p-0 m-0">Welcome Back!</p>
          <p class="subtitle p-0 mt-2 ml-1">Login to your account</p>

          <b-form
            @submit.prevent="formSubmit"
            class="mt-4 av-tooltip tooltip-label-bottom"
          >
            <!-- Email -->
            <b-form-group class="mb-4">
              <b-form-input
                type="text"
                class="custom-field"
                placeholder="Email"
                v-model="$v.form.email.$model"
                :state="!$v.form.email.$error"
              />
              <b-form-invalid-feedback v-if="!$v.form.email.required"
                >Please enter your email address</b-form-invalid-feedback
              >
              <b-form-invalid-feedback v-else-if="!$v.form.email.email"
                >Please enter a valid email address</b-form-invalid-feedback
              >
              <b-form-invalid-feedback v-else-if="!$v.form.email.minLength"
                >Your email must be minimum 4
                characters</b-form-invalid-feedback
              >
            </b-form-group>

            <!-- Password -->
            <b-form-group class="mb-4">
              <b-form-input
                class="custom-field"
                placeholder="Password"
                v-bind:type="showPassword ? 'text' : 'password'"
                v-model="$v.form.password.$model"
                :state="!$v.form.password.$error"
              />
              <b-form-invalid-feedback v-if="!$v.form.password.required"
                >Please enter your password</b-form-invalid-feedback
              >
              <b-form-invalid-feedback
                v-else-if="
                  !$v.form.password.minLength || !$v.form.password.maxLength
                "
                >Your password must be between 4 and 16
                characters</b-form-invalid-feedback
              >
            </b-form-group>

            <b-button
              type="submit"
              variant="primary"
              block
              size="lg"
              :disabled="processing"
              :class="{
                'btn-multiple-state btn-shadow': true,
                'show-spinner': processing,
                'show-success': !processing && loginError === false,
                'show-fail': !processing && loginError,
              }"
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
              <span class="label"
                >{{ $t("user.login-button") }}
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  height="20"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                >
                  <path
                    fill-rule="evenodd"
                    d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z"
                    clip-rule="evenodd"
                  /></svg
              ></span>
            </b-button>

            <div class="mt-4 text-center">
              <router-link tag="a" to="/user/forgot-password">Forgot password?</router-link>
            </div>

            <!-- <div class="social-icons mt-4">
              <b-button class="m-0 p-0" variant="empty">
                <b-img src="/assets/img/login/facebook.png" height="35"></b-img>
              </b-button>
              <b-button class="m-0 p-0" variant="empty">
                <b-img src="/assets/img/login/twitter.png" height="35"></b-img>
              </b-button>
              <b-button class="m-0 p-0" variant="empty">
                <b-img src="/assets/img/login/google.png" height="35"></b-img>
              </b-button>
              <b-button class="m-0 p-0" variant="empty">
                <b-img src="/assets/img/login/vk.png" height="35"></b-img>
              </b-button>
            </div> -->

            <p class="mt-4 text-center">
              Don't have an account ?
              <router-link to="/user/register">Register Now!</router-link>
            </p>
          </b-form>
        </div>
      </div>
    </b-col>
    <b-col lg="7" md="7" sm="12">
      <div class="right-side">
        <!-- <b-img src="/assets/img/login/bg.jpg"></b-img> -->
      </div>
    </b-col>
  </b-row>
</b-container>

</template>

<script>
import { mapGetters, mapActions } from "vuex";
import { validationMixin } from "vuelidate";
import { adminRoot } from "../../constants/config";
const {
  required,
  maxLength,
  minLength,
  email,
} = require("vuelidate/lib/validators");

export default {
  data() {
    return {
      form: {
        email: "",
        password: "",
      },
      showPassword: false,
    };
  },
  mixins: [validationMixin],
  validations: {
    form: {
      password: {
        required,
        maxLength: maxLength(16),
        minLength: minLength(4),
      },
      email: {
        required,
        email,
        minLength: minLength(4),
      },
    },
  },
  computed: {
    ...mapGetters(["currentUser", "processing", "loginError"]),
  },

  mounted() {
    console.log(this.currentUser)
  },
  methods: {
    ...mapActions(["login"]),
    formSubmit() {
      this.$v.$touch();
      // this.form.email = "piaf-vue@coloredstrategies.com";
      // this.form.password = "piaf123";
      this.$v.form.$touch();
      // if (!this.$v.form.$anyError) {
      this.login({
        email: this.form.email,
        password: this.form.password,
      });
      //}
    },
  },
  watch: {
    currentUser(val) {
      if (val && val.uid && val.uid.length > 0) {
        setTimeout(() => {
          this.$router.push(adminRoot);
        }, 200);
      }
    },
    loginError(val) {
      if (val != null) {
        this.$notify("error", "Login Error", val, {
          duration: 3000,
          permanent: false,
        });
      }
    },
  },
};
</script>


<style scoped>
.login-page {
  display: flex;
}

.form-side {
  width: 100%;
  height: 100%;
  padding: 0 1.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  /* align-items: center; */
}

.right-side {
  width: 100%;
  height: 100%;
  background-color: url("/assets/img/login/bg.png");
  background-size: cover;
}

.title {
  font-size: 2rem;
  font-weight: bold;
}

.subtitle {
  font-size: 1rem;
}

.social-icons {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0.8rem;
}

.custom-field {
  border-radius: 25px;
  height: 45px;
  padding: 20px;
}
</style>

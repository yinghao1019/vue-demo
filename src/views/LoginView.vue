<template>
  <div>login page</div>
  <login-form></login-form>
</template>

<script>
import LoginForm from "@/components/LoginForm.vue";

export default {
  data() {
    return {
      isLogin: false,
    };
  },
  components: {
    LoginForm,
  },
  methods: {
    checkLogin() {
      if (localStorage.getItem("email") && localStorage.getItem("password")) {
        this.isLogin = true;
      }
    },
  },
  mounted() {
    this.checkLogin();
    if (this.isLogin) {
      this.$router.push("/");
    }
  },
};
</script>

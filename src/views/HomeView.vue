<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
  </div>
  <input type="button" value="logout" @click="logout" />
</template>

<script>
import { useRouter } from "vue-router";

export default {
  name: "HomeView",
  methods: {
    logout() {
      localStorage.removeItem("email");
      localStorage.removeItem("password");
      this.$router.push("/login");
    },
  },

  mounted() {
    let email = localStorage.getItem("email");
    let password = localStorage.getItem("password");
    if (!email || !password) {
      alert("do not has permission");
      const router = useRouter();
      router.push("/login");
    }
  },
};
</script>

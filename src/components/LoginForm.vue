<template>
  <form>
    <div class="form-column">
      <label for="#email">email</label>
      <input type="email" id="email" v-model="email" required />
    </div>
    <div class="form-column">
      <label for="#password">password</label>
      <input type="password" v-model="password" required />
    </div>
    <button @click="submit">login</button>
  </form>
</template>

<script>
export default {
  name: "LoginForm",
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    submit() {
      localStorage.setItem("email", this.email);
      localStorage.setItem("password", this.password);
      this.email = "";
      this.password = "";

      if (!localStorage.getItem("email") || !localStorage.getItem("password")) {
        alert("login failed");
      } else {
        this.$router.push("/");
      }
    },
  },
};
</script>

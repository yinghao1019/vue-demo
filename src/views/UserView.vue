<template>
  <h1>{{ userId }}</h1>
  <div>username: {{ userInfo.username }}</div>
  <div>email: {{ userInfo.email }}</div>
  <div>phone: {{ userInfo.phone }}</div>
  <hr />

  <div>show</div>
  <router-link :to="`/users/${userId}/posts`">
    /users/{{ userId }}/posts
  </router-link>
  <router-view></router-view>
</template>

<script>
export default {
  data() {
    return {
      userInfo: {},
    };
  },
  methods: {
    async fetchUserInfo(id) {
      return await fetch("https://jsonplaceholder.typicode.com/users/" + id)
        .then((response) => response.json())
        .then((json) => json);
    },
  },
  computed: {
    userId() {
      return this.$route.params.userId;
    },
  },

  watch: {
    userId: async function (val) {
      this.userInfo = await this.fetchUserInfo(val);
    },
  },
  async created() {
    this.userInfo = await this.fetchUserInfo(this.userId);
  },
};
</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
  <p>{{ name }}</p>
</template>

<script>
export default {
  data() {
    return {
      name: this.$route.query.x,
    };
  },
};
</script>

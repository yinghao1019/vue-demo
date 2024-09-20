<template>
  <div>
    <button
      v-for="tab in tabs"
      :key="tab"
      :class="['tab-button', { active: currentTab === tab }]"
      @click="currentTab = tab"
    >
      {{ tab }}
    </button>
  </div>

  <tab-home v-if="currentTab === 'Home'"></tab-home>
  <tab-archive v-if="currentTab === 'Archive'"></tab-archive>
  <tab-posts v-if="currentTab === 'Posts'"></tab-posts>
</template>

<script>
import TabArchive from "./TabArchive.vue";
import TabHome from "./TabHome.vue";
import TabPosts from "./TabPosts.vue";

export default {
  data() {
    return {
      currentTab: "Home",
      tabs: ["Home", "Posts", "Archive"],
    };
  },
  components: {
    TabHome,
    TabArchive,
    TabPosts,
  },
};
</script>

<template>
  <section class="home">
    <h1 class="home__heading">About Nuxtjs Directory Structure</h1>
    <div class="directories">
      <div
        class="directory__container"
        v-for="directory in directories"
        :key="directory.id"
        @click.prevent="storeDirectoryInfo(directory)"
      >
        <p class="directory__name">
          <nuxt-link
            :to="{ name: 'id', params: { id: directory.id, dir: directory } }"
          >{{ directory.name }}</nuxt-link>
        </p>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "about-nuxt",
  data() {
    return {
      directories: [
        //remains the same
      ]
    };
  },
  methods: {
    storeDirectoryInfo(dir) {
      this.$store.commit("saveInfo", {
        directory: dir
      });
    }
  }
};
</script>
<style>
</style>
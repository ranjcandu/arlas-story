<template>
  <div class="page">
    <h3>{{currentPage.text}}</h3>
    <div class="image-wrapper">
      <img :src="currentPage.image">
    </div>
    <div class="action-buttons">
      <button
        v-for="(option, index) in currentPage.options"
        :key="index"
        class="button button-outline action-button"
        @click="setPage(option.toPage)"
      >{{option.text}}</button>
    </div>
  </div>
</template>

<script>
import pages from "../assets/story";
export default {
  data() {
    return {
      pages,
      currentPageNumber: 0
    };
  },
  computed: {
    currentPage() {
      return this.pages[this.currentPageNumber];
    }
  },
  methods: {
    setPage(page) {
      this.currentPageNumber = page;
    }
  },
  name: "Story"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.page {
  display: flex;
  justify-content: space-evenly;
  flex-direction: column;
  padding: 20px;
}

h3 {
  margin: 0;
}

img {
  object-fit: cover;
  max-width: 100%;
  max-height: 60vh;
}

.image-wrapper {
  flex: 1 2 auto;
}

.action-buttons {
  padding: 20px 0;
}

.action-button {
  margin: 10px;
  height: 5rem;
}
</style>

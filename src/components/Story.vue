<template>
  <div class="page">
    <h2>{{currentPage.text}}</h2>
    <div class="image-wrapper">
      <img :src="currentPage.image">
    </div>
    <div class="action-buttons">
      <span
        v-for="(option, index) in currentPage.options"
        :key="index"
        class="action-button"
        @click="setPage(option.toPage)"
      >{{option.text}}</span>
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

h2 {
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
  display: inline-block;
  margin: 10px;
  padding: 20px;
  border: 1px solid #333;
  cursor: pointer;
}
</style>

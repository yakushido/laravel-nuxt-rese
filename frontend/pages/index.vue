<template>
  <div id="app">
    <select class="select">
      <option value="">All genre</option>
      <option v-for="genre in genreLists" :key="genre.id">
        {{genre}}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  data() {
    return {
      genreLists: [],
    };
  },
  methods: {
    async getShop() {
      const resData =await this.$axios.get(
        "http://localhost:8000/api/shop/"
      );
      this.genreLists = resData.data.genreLists;
    }
  },
}
</script>

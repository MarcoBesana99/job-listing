<template>
    <div class="flex justify-center mb-6">
      <input v-model="searchQuery" @input="query" class="p-2 w-full shadow-xl" type="text">
    </div>
</template>

<script>

export default {
  data() {
    return {
      searchQuery : ''
    };
  },
  methods: {
    query() {
      this.$emit('search', this.searchQuery)
    }
  },
};
</script>

<style scoped>
</style>
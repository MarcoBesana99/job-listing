<template>
  <nav class="h-24 relative">
    <img
      class="absolute top-0 left-0 w-full h-full hidden sm:block"
      src="@/assets/images/bg-header-desktop.svg"
      alt="header design"
    />
    <img
      class="absolute top-0 left-0 w-full h-full block sm:hidden"
      src="@/assets/images/bg-header-mobile.svg"
      alt="header design"
    />
  </nav>
</template>

<script>
export default {};
</script>

<style scoped>
nav {
  background-color: #5da5a4;
}
</style>
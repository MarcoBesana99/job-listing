<template>
  <div
    class="
      rounded
      bg-white
      mb-10
      lg:mb-5
      p-8
      shadow-xl
      job-card
      flex flex-col
      lg:flex-row
      justify-between
      relative
    "
  >
    <div class="flex flex-col lg:flex-row">
      <img
        class="mr-5 absolute w-14 -top-6 lg:top-0 lg:w-24 lg:relative"
        :src="require('@/assets' + job.logo.replace('.', ''))"
        :alt="job.company"
      />
      <div>
        <div class="flex mt-2 lg:mt-0">
          <h3 class="mr-4 font-semibold job-company">{{ job.company }}</h3>
          <span
            class="
              mr-2
              text-white
              rounded-full
              px-2
              flex
              items-center
              font-semibold
              new-pill
            "
            v-if="job.new"
            >New</span
          >
          <span
            class="
              text-white
              bg-gray-800
              rounded-full
              px-2
              flex
              items-center
              font-semibold
            "
            v-if="job.featured"
            >Featured</span
          >
        </div>
        <h2
          class="
            font-semibold
            hover:main-text-color
            job-position
            cursor-pointer
            text-lg
            my-1
          "
        >
          {{ job.position }}
        </h2>
        <span class="text-gray-500">{{
          job.postedAt + " • " + job.contract + " • " + job.location
        }}</span>
      </div>
    </div>
    <div class="flex items-center lg:flex-nowrap flex-wrap lg:border-t-0 border-t mt-4 lg:mt-0 border-gray-300">
      <span
        class="mr-3 categories font-semibold rounded px-2 flex items-center mt-4 lg:mt-0"
        >{{ job.level }}</span
      >
      <span
        class="mr-3 categories font-semibold rounded px-2 flex items-center mt-4 lg:mt-0"
        v-for="(lang, index) in job.languages"
        :key="index"
        >{{ lang }}</span
      >
      <span
        class="mr-3 categories font-semibold rounded px-2 flex items-center mt-4 lg:mt-0"
        v-for="(tool, index) in job.tools"
        :key="index"
        >{{ tool }}</span
      >
    </div>
  </div>
</template>

<script>
export default {
  props: {
    job: Object,
  },
};
</script>

<style scoped>
.job-card:last-of-type {
  margin-bottom: 0 !important;
}
.job-position:hover,
.job-company {
  color: #5fa3a4;
}
.new-pill {
  background-color: #5fa3a4;
}
.categories {
  background-color: #eef7f6;
  color: #5fa3a4;
  cursor: pointer;
}

.categories:hover {
  background-color: #5fa3a4;
  color: white !important;
}
</style>
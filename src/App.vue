<template>
  <div>
    <Header></Header>
    <div class="lg:px-28 lg:py-14 py-14 px-8">
      <JobCard v-for="job in jobs" :job="job" :key="job.id"></JobCard>
    </div>
  </div>
</template>

<script>
import data from "@/json/data.json";
import JobCard from "@/components/JobCard";
import Header from "@/components/Header";

export default {
  name: "App",
  data() {
    return {
      jobs: data,
    };
  },
  components: {
    JobCard,
    Header
  },
};
</script>

<style>
body {
  background-color: #F0FAFB;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>

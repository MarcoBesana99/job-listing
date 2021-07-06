<template>
  <div>
    <Header></Header>
    <JobCard v-for="job in jobs" :job="job" :key="job.id"></JobCard>
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
</style>

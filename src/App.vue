<template>
  <div>
    <job-card v-for="job in jobs" :job="job" :key="job.id"></job-card>
  </div>
</template>

<script>
import data from "@/json/data.json";
import JobCard from "@/components/JobCard";

export default {
  name: "App",
  data() {
    return {
      jobs: data,
    };
  },
  components: {
    JobCard
  },
};
</script>

<style>
</style>

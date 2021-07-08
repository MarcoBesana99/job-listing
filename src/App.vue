<template>
  <div>
    <Header></Header>
    <div class="lg:px-28 lg:py-14 py-14 px-8">
      <Search @search="updateJobList"></Search>
      <JobCard v-for="job in jobs" :job="job" :key="job.id"></JobCard>
    </div>
  </div>
</template>

<script>
import data from "@/json/data.json";
import JobCard from "@/components/JobCard";
import Header from "@/components/Header";
import Search from "@/components/Search";

export default {
  name: "App",
  data() {
    return {
      jobs: data,
      filteredJobs: [],
      Ids: [],
    };
  },
  components: {
    JobCard,
    Header,
    Search,
  },
  methods: {
    updateJobList(e) {
      this.jobs = data;
      this.filteredJobs = [];
      this.Ids = [];
      if (e == "") {
        return;
      } else {
        e.trim().split(" ").forEach((word) => {
          this.jobs.forEach((job) => {
            if (
              !this.Ids.includes(job.id) &&
                (job.position.toLowerCase().includes(word.toLowerCase()) ||
              job.role.toLowerCase().includes(word.toLowerCase()))
            ) {
              this.filteredJobs.push(job);
              this.Ids.push(job.id);
            }
          });
        });
        this.jobs = this.filteredJobs;
      }
    },
  },
};
</script>

<style>
body {
  background-color: #f0fafb;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>

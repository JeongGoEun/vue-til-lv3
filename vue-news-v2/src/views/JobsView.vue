<template>
  <div>
    <div v-for="job in jobs" :key="job.id"> {{ job.title }} </div>
  </div>
</template>

<script>
import { fetchJobsList } from '../api/index'

export default {
  data() {
    return {
      jobs: []
    }
  },
  created() {
    fetchJobsList().then((res) => { this.jobs = res.data });
  }
} 
</script>

<style>

</style>

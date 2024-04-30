<template>
  <div>
    <JobList :jobs="jobs" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import JobList from './components/JobList.vue'
import type { Job } from './types/Job'

export default defineComponent({
  name: 'App',
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'riverdale ranch', salary: 30000, id: 1 },
      { title: 'warehouse packer', location: 'amazon', salary: 40000, id: 2 },
      { title: 'plumber', location: 'rocket toilets', salary: 50000, id: 3 },
      { title: 'driver', location: 'lift', salary: 25000, id: 4 },
      { title: 'fisherman', location: 'riverdale ranch', salary: 23000, id: 5 },
      { title: 'project manager', location: 'officair', salary: 70000, id: 6 },
    ])

    return { jobs }
  }
});
</script>

<style scoped></style>

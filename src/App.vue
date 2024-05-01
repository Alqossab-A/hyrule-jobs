<template>
  <div class="app">
    <h1>Joes Jobs</h1>
    <header>
      <div class="order">
        <button @click="handleClick('title')">Sort by title</button>
        <button @click="handleClick('location')">Sort by location</button>
        <button @click="handleClick('salary')">Sort by salary</button>
      </div>
    </header>
    <JobList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import JobList from './components/JobList.vue'
import type { Job } from './types/Job'
import type { OrderTerm } from './types/OrderTerm'

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
    ]);

    const order = ref<OrderTerm>('title');

    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };

    return { jobs, handleClick, order };
  }
});
</script>

<style scoped>
header {
  text-align: center;
}

header .order {
  margin-top: 20px;
}

h1 {
  text-align: center;
}

button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>

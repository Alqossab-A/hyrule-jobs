<template>
  <p>{{ name }} - {{ age }}</p>
  <button @click="changeName('zelda'), changeAge(33)">change name</button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

export default defineComponent({
  name: 'App',
  components: {},
  data() {
    return {
      name: 'Link',
      age: 25 as number | string,
    }
  },
  methods: {
    changeName(name: string) {
      this.name = name;
    },
    changeAge(age: number | string) {
      this.age = age;
    }
  },
});
</script>

<style scoped></style>

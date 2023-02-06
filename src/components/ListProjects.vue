<script>
import axios from "axios";
export default {
  name: "ListProjects",
  data() {
    return {
      projects: [],
    };
  },
  created() {
    axios.get("http://127.0.0.1:8000/api/projects").then((response) => {
      this.projects = response.data;
    });
  },
};
</script>

<template>
  <h2>List Projects</h2>
  <ul>
    <li v-for="project in projects">
      {{ project.name }}
    </li>
  </ul>
</template>

<style lang="scss" scoped></style>

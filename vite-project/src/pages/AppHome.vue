<template>

<div class="row justify-content-between">
  <ProjectCard
  v-for="project in projects"
  :key="project.id"
  :project="project"

  class="col-3 my-2"

  @click="toProjectShow(project.id)"
  />
  
</div>

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import ProjectCard from '../components/ProjectCard.vue';
import axios from 'axios';

export default {
  name: 'AppHome',

  components: {
    ProjectCard
  },

  data() {
    return {
      projects: []
    }
  },
  methods: {

    toProjectShow(id){
    this.$router.push("/projects/" + id)

  },
  },
  
  mounted() {
    axios.get("http://127.0.0.1:8000/api/v1/projects")
    .then(response => {

      console.log(response.data.projects)

      this.projects = response.data.projects
    })
    .catch(error => {
      console.log(error)
    })
  }


}
</script>
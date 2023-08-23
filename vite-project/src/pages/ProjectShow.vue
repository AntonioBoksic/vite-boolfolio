<template>

    <h1>Project SHOW</h1>

    <h2>Project {{ project.name }}</h2>
    <p>{{ project.description }}</p>
    <div class="row">
    <span class="col">device: {{ project.device }}</span>
    <span class="col">programming language: {{ project.programming_language }}</span>
    <span class="col">type: {{ project.type.name }}</span>
    <span class="col">technologies: {{ project.technologies.name }}</span>




</div>


</template>

<script>
import axios from 'axios';

export default {
    name: 'ProjectShow',
    data() {
        return {
            project: {}
        }
    },
    mounted() {
        const projectId = this.$route.params.id;
        // console.log(projectId)
        axios.get("http://127.0.0.1:8000/api/v1/projects/" + projectId)
        .then(res => {

            const data = res.data.project;
            console.log(data)
            this.project = data
        })
        .catch(err => {
            console.log(err)

        })
    }
}
</script>
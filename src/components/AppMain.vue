<script>
import axios from 'axios';
import ProjectCard from './ProjectCard.vue';

export default {

    data() {
        return {
            baseUrl: 'http://127.0.0.1:8000',
            projects: [],
        }
    },
    created() {
        axios.get(`${this.baseUrl}/api/projects`)
            .then((resp) => {
                this.projects = resp.data.result.data
                // console.log(resp.data.result.data);
            })
    },
    components: { ProjectCard },
}

</script>
<template>
    <div class="container">
        <div class="row row-cols-3">
            <div class="col" v-for="project in projects">

                <ProjectCard :project="project" />

            </div>
        </div>
    </div>
</template>

<style scoped lang="scss"></style>
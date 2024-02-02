<script>
import axios from 'axios';
import ProjectCard from '../components/ProjectCard.vue';
import { store } from '../store';

export default {

    data() {
        return {
            store,
            projects: [],
        }
    },
    created() {
        axios.get(`${this.store.baseUrl}/api/projects`)
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
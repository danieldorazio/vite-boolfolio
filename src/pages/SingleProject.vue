<script>
import axios from 'axios';
import { store } from '../store';

export default {
    data() {
        return {
            store,
            curProject: null,
            loading: false,
        }
    },
    created() {
        
        this.loading = true;
        axios
            .get(`${this.store.baseUrl}/api/projects/${this.$route.params.slug}`)
            .then((resp) => {
                this.curProject = resp.data.result;
                console.log(this.curProject);
            })
            .finally(() => {
                this.loading = false;
            });
    },
};
</script>

<template>
    <div class="container mt-4">
        <div v-if="loading">
            <h3>Loading...</h3>
        </div>
        <div v-else>
            <div class="card m-auto " style="width: 18rem;">
                <img :src="`${store.baseUrl}/storage/${curProject.cover_image}`" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title"> {{ curProject.title }}</h5>
                    <p class="card-text"> {{ curProject.description }}</p>
                </div>
                <ul class="list-group list-group-flush">
                    <li class="list-group-item"> {{ curProject.user.name }}</li>
                    <li class="list-group-item"> {{ curProject.type.name }}</li>
                    <li class="list-group-item"> {{ curProject.type.typology }}</li>
                    <li v-for="tecnology  in curProject.tecnologies" class="list-group-item"> {{ tecnology.name }}</li>
                </ul>
            </div>

        </div>
    </div>
</template>

<style></style>
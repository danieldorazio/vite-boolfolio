<script>
export default {
    props: {
        project: Object,
    },
    computed: {
        truncateText () {
            if (this.project.description && this.project.description.length > 150) {
                return this.project.description.substring(0, 150) + "...";
            }
            return this.project.description;
        }
    }
}
</script>

<template>
    <div class="card" style="width: 18rem;">
        <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            <h6 class="card-subtitle mb-2 text-body-secondary">{{ project.slug }}</h6>
            <p class="card-text">{{ truncateText }}</p>
            <router-link :to="{ name: 'single-project', params: {slug: project.slug}}">DETTAGLI</router-link>
        </div>
    </div>
</template>

<style scoped lang="scss"></style>
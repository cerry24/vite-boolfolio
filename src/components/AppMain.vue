<script>
import axios from 'axios';
import { store } from '../store'
import ProjectCard from './ProjectCard.vue'

export default {
    name: 'AppMain',

    components: {
        ProjectCard
    },

    data() {
        return {
            store,
            apiUrl: 'http://127.0.0.1:8000/api/projects'
        }
    },

    methods: {
        getProjects() {
            axios.get(this.apiUrl, {
            params: {
            }
        })
        .then((response) => {
            console.log(response.data.results.data);
            store.projects = response.data.results.data;
        })
        .catch(function (error) {
            console.warn(error);
        });
        }
    },

    created() {
        this.getProjects();
    },
}
</script>

<template>
<section id="cards">
    <div class="container">
        <div class="row">
            <ProjectCard v-for="project in store.projects" :project="project" />
        </div>
    </div>
</section>
</template>

<style lang="scss" scoped>
    
</style>
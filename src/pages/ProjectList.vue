<script>
import axios from 'axios';
import { store } from '../store';
import ProjectCard from '../components/ProjectCard.vue';

export default {
    name: 'ProjectList',

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
                'api_token': 'gnXDEhycV9OtAGbltR8bMRVECjc1ubmE58HJP88dUwNVs7giSuqE9Je552uqKMSj22AzsEpiTDKu9rlV'
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
    <div class="row justify-content-evenly">
        <ProjectCard v-for="project in store.projects" :project="project" class="col-5 my-3 p-0"/>
    </div>
</template>

<style lang="scss" scoped>
    
</style>
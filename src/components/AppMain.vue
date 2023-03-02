<script>
import axios from 'axios';
import { store } from '../store'

export default {
    name: 'AppMain',

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

</template>

<style lang="scss" scoped>
    
</style>
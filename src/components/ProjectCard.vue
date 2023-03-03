<script>
import { store } from '../store';

export default {
    name: 'ProjectCard',
    
    props: {
        project: {
            type: Object,
            required: true
        }
    },
    
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <article class="card">
        <img :src="project.thumbnail" class="card-img-top" alt="project thumbnail">
        <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <p class="card-text">Type: {{ project.type.name }}</p>
            <span class="badge rounded-pill text-bg-success me-2" v-for="technology in project.technologies">{{ technology.name }}</span>
        </div>
        <div class="card-footer d-flex justify-content-center">
            <a href="#" class="btn btn-primary">show more</a>
        </div>
    </article>
</template>

<style lang="scss" scoped>
</style>
<script setup>
import { lessons } from '@/db.json'
import LessonSingle from './LessonSingle.vue';
</script>

<template>
    <section class="Lessons">
        <div class="title">
            <p class="completion">1/6</p>
            <h2>Lessons</h2>
            <p class="date">14.01.2024</p>
        </div>
        <div class="sectionInner">
            <template v-for="lesson, index in lessons" :key="lesson.id">
                <LessonSingle :lesson="lesson" :index="index" />
            </template>
        </div>
    </section>
</template>



<style lang="scss" scoped>
.Lessons {
    grid-column: 1/4;
    grid-row: 1/2;

    .sectionInner {
        padding: 20px;
    }
}
</style>
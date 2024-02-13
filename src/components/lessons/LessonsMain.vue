<script setup>
import { lessons } from '@/db.json'
import LessonSingle from './LessonSingle.vue';
</script>

<template>
    <ol>
        <li v-for="lesson in lessons" :key="lesson.id">
            <LessonSingle :lesson="lesson" />
        </li>
    </ol>
</template>



<style lang="scss" scoped></style>
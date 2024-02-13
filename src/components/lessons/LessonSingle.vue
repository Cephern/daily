<script setup>
import { computed } from 'vue';

const props = defineProps({
    lesson: Object,
})

const { name, duration, category, currentTime, active } = props.lesson

const timePercent = computed(() => Math.floor((currentTime / duration) * 100))
</script>

<template>
    <div class="lessonUpper">
        <p class="name">{{ name }}</p>
        <p v-show="active" class="time">
            <span class="duration">{{ currentTime }}</span>/
            <span class="currentTime">{{ duration }}</span> <span class="percentage">({{ timePercent }}%)</span>
        </p>
    </div>
    <span class="category">{{ category }}</span>
</template>

<style scoped>
.lessonUpper {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
}
</style>
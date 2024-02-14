<script setup>
import { computed } from 'vue';

const props = defineProps({
    lesson: Object,
    index: Number
})

const { name, duration, category, currentTime, active } = props.lesson

const timePercent = computed(() => Math.floor((currentTime / duration) * 100))
</script>

<template>
    <div class="lesson">
        <div class="lessonUpper">
            <span class="index">{{ index + 1 }}</span>

            <p>{{ name }}</p>

            <span v-if="!active" class="duration">{{ duration }}min</span>
        </div>

        <div v-if="active" class="lessonLower">
            <span class="controls">{{ isPlaying ? '|>' : '||' }}</span>

            <div class="progress">
                <div class="progressStats">
                    <span class="time">{{ currentTime }}/{{ duration }} min</span>
                    <span class="percent">{{ timePercent }}%</span>
                </div>

                <div class="progressBar">
                    <div class="progressInner"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.lesson {
    width: 300px;
    margin: 12px 0;
    color: #fff;
    background-color: #0C3D58;
    border-top-right-radius: 12px;
    border-bottom-left-radius: 12px;

    .lessonUpper {
        height: 30px;
        text-align: center;
        gap: 10px;
        position: relative;

        p {
            font-size: 20px;
            text-transform: capitalize;
        }

        .index {
            position: absolute;
            top: -12px;
            left: -12px;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            background-color: #E37A59;
            text-align: center;
        }

        .duration {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 12px;
        }
    }

    .lessonLower {
        position: relative;
        padding-bottom: 8px;

        .controls {
            position: absolute;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
        }


        .progress {
            width: 220px;
            margin: 0 auto;

            .progressStats {
                display: flex;
                justify-content: space-between;
                width: 100%;
            }

            .progressBar {
                width: 100%;
                height: 4px;
                background-color: #fff;
                border-radius: 4px;
                font-size: 12px;

                .progressInner {
                    width: 56%;
                    height: 100%;
                    background-color: #229478;
                    border-radius: 4px;
                }
            }
        }
    }
}
</style>
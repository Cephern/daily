<script setup>
import LessonsMain from '@/components/lessons/LessonsMain.vue'
import FundsMain from '@/components/funds/FundsMain.vue'
import DailyMain from '@/components/daily/DailyMain.vue'
import WeatherMain from '@/components/weather/WeatherMain.vue'

</script>

<template>
  <div class="wrapper">
    <LessonsMain />
    <WeatherMain />
    <DailyMain />
    <FundsMain />
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  justify-items: center;
  gap: 20px;
}
</style>

<script setup>
import LessonsMain from '@/components/lessons/LessonsMain.vue'
import FundsMain from '@/components/funds/FundsMain.vue'
import DailyMain from '@/components/daily/DailyMain.vue'
import UserStats from '@/components/userStats/UserStats.vue'

</script>

<template>
  <header class="main-color">
    <div class="logo">Logo</div>
    <div class="notch">Notch</div>
    <nav>
      Navigation
    </nav>
  </header>

  <div class="wrapper main-color">
    <LessonsMain />
    <UserStats />
    <DailyMain />
    <FundsMain />
  </div>

  <footer>
    Cephern&trade; 2024
  </footer>
</template>

<style lang="scss" scoped>
header {
  width: 100%;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;

}

.wrapper {
  width: 1440px;
  height: calc(100vh - 160px);
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(2, 1fr);
  justify-items: center;
  place-items: center;
  gap: 40px;
  margin: 0 auto;
  border-bottom-left-radius: 20px;
  border-bottom-right-radius: 20px;
  padding: 20px;
}

footer {
  width: 1440px;
  height: 60px;
  margin: 20px auto 0;
  text-align: center;
}
</style>

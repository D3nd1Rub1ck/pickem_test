<script setup lang="ts">
// import HelloWorld from './components/HelloWorld.vue'
import GroupSection from './components/GroupSection.vue';
import Header from './components/Header.vue';
import { ref, onMounted } from "vue";

const data = ref(null);

onMounted(async () => {
  try {
    const response = await fetch("/testData/pickem_test.json"); // Путь относительно public
    data.value = await response.json();
  } catch (error) {
    console.error("Ошибка загрузки JSON:", error);
  }
});

</script>

<template>
  <main>
    {{ data }}
    <div class="section">
      <Header></Header>
    </div>
    <div class="section">
      <GroupSection :groupName="'Группа A'" :score="1200" :max-score="1600"/>
    </div>
    <div class="section">
      <GroupSection :groupName="'Группа Б'" :score="1200" :max-score="1600"/>
    </div>
  </main>
</template>

<style scoped>

main {
  /* width: 100%; */
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  gap: 20px;

  padding: 0px 200px;
}

.section {
  width: 100%;
  /* width: fit-content; */
  height: fit-content;

  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;

  padding: 15px 35px;
  border-radius: 20px;

  background: #191F26;
}
</style>

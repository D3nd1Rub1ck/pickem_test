<script setup lang="ts">
import Branch from './icons/branch.vue';
import lineBar from './icons/line-bar.vue';
import lineHome from './icons/line-home.vue';
import groups from './icons/Groups.vue';
import Medal from './icons/medal.vue';
</script>

<template>
    <div class="header">
      <div class="item selected">
        <lineHome />
        Главная 
      </div>
      <div class="divider"></div>
      <div class="item">
        <groups />
        Группы
      </div>
      <div class="divider"></div>
      <div class="item">
        <lineBar />
        Лидерборд 
      </div>
      <div class="divider"></div>
      <div class="item">
        <Branch />
        Номинации
      </div>
      <div class="divider"></div>
      <div class="item">
        <Medal />
        Плей-офф
      </div>
    </div>
</template>

<style scoped>
.header {
    width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 15px;
  padding: 20px;
}

.item {
  display: flex;
  gap: 5px;
  align-items: center;
  color: white;
  font-size: 1.2rem;
  cursor: pointer;
  padding: 5px 15px;
  border-radius: 10px;
  position: relative;
  transition: background-color 0.3s ease-in-out, transform 0.2s ease;
}

.selected {
  background: rgba(249, 250, 251, 0.1);
}

.divider {
  background: rgb(255, 255, 255, 0.2);
  width: 4px;
  border-radius: 2px;
  height: 40px;
}

.item:hover {
  background: rgba(249, 250, 251, 0.2);
  transform: translateY(-2px);
}

.item:active {
  background: rgba(249, 250, 251, 0.3);
  transform: scale(0.98);
}
</style>

<script setup lang="ts">
import Card from './Card.vue'
</script>

<template>
  <div class="wrapper"> 
    <div class="table">
      <div class="column">
        <div class="header">
          Раунд 1 
        </div>
        <div class="content">
          <Card class="test" :date="new Date('2025-03-27T00:00:00Z')" />
          <Card class="test" :date="new Date('2025-03-27T00:00:00Z')" />
          <Card class="test" :date="new Date('2025-03-27T00:00:00Z')" />
          <Card class="test" :date="new Date('2025-03-27T00:00:00Z')" />
        </div>
      </div>
      <div class="column">
        <div class="header">
          Раунд 2 
        </div>
        <div class="content">
          <Card class="test" :date="new Date('2025-03-28T00:00:00Z')" />
          <Card class="test" :date="new Date('2025-03-27T00:00:00Z')" />
        </div>
      </div>
      <div class="column">
        <div class="header">
          Раунд 3 
        </div>
        <div class="content">
          <Card class="test" :date="new Date('2025-03-27T00:00:00Z')" />
        </div>
      </div>
      <div class="column">
        <div class="header">
          Winner
        </div>
        <div class="content">
          <Card class="test" :date="new Date('2025-03-27T00:00:00Z')" :winner="true"/>
        </div>
        
      </div>
    </div>
  </div>
</template>


<style scoped>
.wrapper {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 25px;
}

.table {
  min-height: fit-content;
  position: relative;
  display: flex;
  gap: 0px;
}

.header {
  width: 100%;  
  padding: 5px;
  border-radius: 7.5px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background: #313840;
  color: rgb(255, 255, 255, 0.8);
}

.stage::before {
  content: '';
  height: 100%;
  width: 2px;
  background: #191F26;
}

.column {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  gap: 30px;
  /* position: relative; */
}

.content {
  height: 100%;
  margin: 0px 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  gap: 30px;
}

/* .test {
  position: relative;
  min-height: 80px; Примерная высота карточки
} */

/* Линии для левой колонки */
/* .test::after { .column:first-child
  content: '';
  position: absolute;
  top: 50%;
  left: 100%;
  width: 25px;
  border-top: 2px solid gray;
} */

/* .test:nth-child(odd)::before { /*.column:first-child * /
  content: '';
  position: absolute;
  top: 50%;
  left: calc(100% + 25px);
  height: 85%; /* Высота вертикального сегмента * /
  width: 25px; /* Ширина горизонтального сегмента * /
  border-left: 2px solid gray;
  border-bottom: 2px solid gray;
} */

/* .test:nth-child(even)::before { /*.column:first-child * /
  content: '';
  position: absolute;
  top: -35%;
  left: calc(100% + 25px);
  height: 85%; /* Высота вертикального сегмента * /
  width: 25px; /* Ширина горизонтального сегмента * /
  border-left: 2px solid gray;
  border-top: 2px solid gray;
} */


/* .column:last-child .test::after {
  content: '';
  position: absolute;
  top: 50%;
  right: 100%;
  width: 25px;
  border-top: 2px solid gray;
} */


/* .column:first-child .test:nth-child(n+3)::before {
  display: none;
} */
</style>
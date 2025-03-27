<script setup lang="ts">
import Cross from './icons/cross.vue';
import Random from './icons/random.vue';
import TournamentBracket from './TournamentBracket.vue'

defineProps<{
  groupName?: string;
  score? : number;
  maxScore? : number;
}>();

</script>

<template>
    <div class="title">
    <h1>{{groupName ? groupName : "Группа"}}</h1>
    <span class="counter"> 
        {{score ? score : "x"}} 
        / 
        {{maxScore ? maxScore : "y"}} 
    </span>
    </div>
    <TournamentBracket />
    <div class="divider" /> 
    <div class="actions">
    <div>
        <button class="random">
        <Random />
        Случайно
        </button>
        <button class="clear">
        <Cross /> 
        Сбросить
        </button>  
    </div>
    <button class="accept">
        Подтвердить
    </button>
    </div>
</template>

<style scoped>
.title{
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  gap: 10px;
}

.title h1 {
  margin: 10px;
  color: aliceblue;
}

.counter {
  padding: 5px 10px;
  border-radius: 5px;
  background: rgba(45, 225, 152, 0.3);
  color: #2DE198;
  position: relative;
}

.counter::after {
  content: "";
  position: absolute;
  width: 60%;
  height: 10%;
  left: 50%;
  top: 0px;
  transform: translateX(-50%);
  border-bottom: 3px solid #2DE198;
  box-sizing: border-box; 
  border-radius: 2px;
}

.actions {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.actions button{
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  gap: 5px;

  /* border: none; */
  padding: 10px 20px;
  border-radius: 10px;
  font-family: 'Segoe UI';
  font-weight: 600;
  font-size: 12px;
}

.actions div{
  display: flex;
  gap: 15px;
}

.divider {
  width: 100%;
  height: 2px;
  border-radius: 1px;
  background: rgb(255, 255, 255, 0.3);
  margin: 50px 0px 20px;
}

.random {
  color: rgb(255 255 255 / 80%);
  border: 2px solid #2DE198;
  background: rgb(45 225 152 / 30%);
  transition: all 0.25s ease;
}
.random:hover {
  background: rgb(45 225 152 / 40%);
  box-shadow: 0 0 8px rgb(45 225 152 / 20%);
}
.random:active {
  transform: scale(0.98);
  background: rgb(45 225 152 / 50%);
}

.clear {
  color: rgb(255 255 255 / 80%);
  border: none;
  background: rgb(67 74 84 / 50%);
  transition: all 0.25s ease;
}
.clear:hover {
  background: rgb(67 74 84 / 60%);
}
.clear:active {
  transform: scale(0.98);
  background: rgb(67 74 84 / 70%);
}

.accept {
  color: #0D1117;
  border: none;
  background: #2DE198;
  transition: all 0.25s ease;
}
.accept:hover {
  background: #25C583;
  box-shadow: 0 2px 8px rgb(45 225 152 / 30%);
}
.accept:active {
  transform: scale(0.98);
  background: #1EAE74;
}

</style>

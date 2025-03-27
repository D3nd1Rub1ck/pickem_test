<script setup lang="ts">
import { defineComponent, h } from 'vue';
import IconLines from './icons/IconLines.vue';

defineProps<{
  points?: number;
  date?: Date;
  title?: string;
  logo?: string; // src
  winner?: boolean;
}>();

const Team = defineComponent({
  name: 'Team',
  props: {
    title: {
      type: String,
      default: 'Team'
    },
    logo: {
      type: String,
      default: 'https://cdn-icons-png.flaticon.com/16/1178/1178479.png'
    }
  },
  setup(props) {
    return () =>
      h('div', { class: 'team' }, [
        h('img', { src: props.logo, alt: 'team logo' }),
        h('span', { class: 'title' }, props.title)
      ]);
  }
});
</script>

<template>
  <div class="card">
    <div class="header">
      <div class="date" v-if="winner">
        Победитель
        </div>
      <div class="date" v-if="!winner">
        {{ date ? date.toLocaleString('ru-RU', { hour: '2-digit', minute: '2-digit', day: '2-digit', month: 'short' }).replace(',', '') : 'N/A' }}
      </div>
      <div class="icon" v-if="!winner">
        <IconLines />
        + <span> {{ points ? points : 200}} </span>
      </div>
    </div>
    
    <Team />
    <Team v-if="!winner"/>
  </div>
</template>

<style scoped>
.card{
    border: 1px solid rgb(255, 255, 255, 0.5);;
    border-radius: 5px;
    padding: 10px;
    min-width: 180px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 5px;
    color: rgb(255, 255, 255, 0.7);
}

.header{
  width: 100%;
  color: rgb(255, 255, 255, 0.65);
  display: flex;
  justify-content: space-between;
}

.icon {
  width: 60px;
  color: black;
  background: #2DE198;
  text-align: center;
  vertical-align: middle;
  border-radius: 2px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.team {
  padding: 5px;
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 10px;
  border-radius: 5px;
  background: #313840;
}
</style>

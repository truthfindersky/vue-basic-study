<template>

  <IopSlot>
    <!-- 1 -->
    <template v-slot:listitem>
      <ul>
        <li v-for="li in list" :key="li">
          {{li}}
        </li>
      </ul>
    </template>

    <!-- 2 -->
    <template v-slot:listname>
    </template>

    <!-- 3 -->
    <template v-slot:anotherList="slotProps">
      {{slotProps.firstName}} : {{slotProps.lastName}}
    </template>

  </IopSlot>
</template>

<script>
import IopSlot from './components/IopSlot.vue'

export default {
  name: 'AppIopSlot',
  data() {
    return {
      list: ['HTML', 'CSS', 'JavaScript']
    }
  },
  components: {
    IopSlot
  }
}
</script>

<style>
#AppSlotProps {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>

<script setup lang='ts'>
import { Data } from '../types/type';


const props = defineProps<{
  lists: Data[]
}>()

const emit = defineEmits(['delete'])


const deleteData = (id: number) => {
  const filteredData = props.lists.filter(t => t.id != id)
  emit('delete', filteredData)
}


</script>

<template>
  <ul>
    <li v-for="list in props.lists" :key="list.id">
      {{ list.memo }}
      <button @click="deleteData(list.id)">DEL</button>
    </li>
  </ul>
</template>


<style scoped></style>

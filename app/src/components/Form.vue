<script setup lang='ts'>
import { ref, Ref } from "vue";
import { Data } from "../types/type";



const props = defineProps<{
  lists: Data[]
}>()


const desc: Ref<string> = ref("")
let id = 0

const submitData = () => {
  id++
  props.lists.push({
    memo: desc.value,
    id: id
  })
  console.log(props.lists);
  desc.value = ""
}

</script>
<template>
  <form @submit.prevent="submitData">
    <input v-model="desc">
    <button>ADD</button>
  </form>
</template>


<style scoped></style>

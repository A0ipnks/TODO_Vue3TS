<script setup lang='ts'>
import { Ref, ref } from "vue";
import FormComp from "../src/components/Form.vue";
import List from "./components/List.vue";
import { Data } from "./types/type";

const lists: Ref<Data[]> = ref([])

const deleteData = (updatedData: Data[]) => {
  lists.value = updatedData
  console.log(lists.value);
}

</script>

<template>
  <FormComp :lists="lists"></FormComp>
  <List :lists="lists" @delete="deleteData"></List>
</template>


<style></style>

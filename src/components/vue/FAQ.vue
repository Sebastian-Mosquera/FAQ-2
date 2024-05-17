<script setup>
import { ref } from 'vue'

const data = ['Tema 1', 'Tema 2', 'Tema 3', 'Tema 4']

const selectedIndex = ref(0)

function showInfo(i) {
  if(i == selectedIndex.value) {
    selectedIndex.value = -1
  } else {
    selectedIndex.value = i
  }
}
</script>
<template>
    <div
      class="bg-blue-500 p-1 max-w-60 mx-auto mt-12"
    >
      <div
        class="mb-1"
        v-for="(theme, i) in data"
        :key="i"
      >
        <h1 
          @click="showInfo(i)"
          class="select-none hover:cursor-pointer bg-blue-400 text-white px-1 flex justify-between"
          :class="{'bg-blue-800': selectedIndex == i}"
        >
          {{ theme }}
          <span>{{ selectedIndex == i ? '-' : '+' }}</span>
        </h1>
        <div
          v-show="selectedIndex == i"
          class="bg-blue-50/50 p-1 mt-1"
        >
          Texto del tema 1
        </div>
      </div>
    </div> 
</template>
<template>
  <div class="relative isolate overflow-hidden bg-gradient-to-b from-indigo-100/20 pt-10">
    <div class="mx-auto max-w-2xl lg:text-center">
      <p class="mt-2 text-5xl font-semibold tracking-tight text-gray-800" style="font-family: 'Rubik'">What we do</p>
      <p class="mt-6 text-lg leading-8 text-gray-600">Our groundbreaking service combines Generative AI and human expertise to ensure top-quality customer experience</p>
    </div>
    <div class="mx-auto max-w-7xl px-6 pb-24 pt-10 sm:pb-32 lg:flex lg:px-8 lg:py-20">
      <div class="mx-auto max-w-3xl flex-shrink-0 lg:mx-0 lg:max-w-2xl">
        <div v-for="item in items" :class="['my-12 pl-4 cursor-pointer', item.selected ? 'border-l-4 border-indigo-600' : 'ml-1']" @click="onSelectItem(item)">
          <div :class="['my-2 text-gray-600 text-3xl hover:text-indigo-600', item.selected ? 'text-indigo-600' : '']" style="font-family: 'Rubik'">{{ item.name }}</div>
          <div v-if="item.selected" class="text-gray-600 text-lg">{{ item.description }}</div>
        </div>
      </div>
      <div class="mx-auto mt-16 max-w-2xl sm:mt-24 lg:ml-10 lg:mr-0 lg:mt-0 lg:max-w-none lg:flex-grow">
        <img :src="selectedImage" alt="" class="mt-5 aspect-[5/5] w-full max-w-lg rounded-2xl object-cover sm:mt-16 lg:mt-0 lg:max-w-none xl:row-span-2 xl:row-end-2" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ChevronRightIcon } from '@heroicons/vue/20/solid';
import { ref, reactive, computed } from 'vue';

const items = computed(() => [
  {
    id: 0,
    name: 'Generative AI',
    description: 'Quis tellus eget adipiscing convallis sit sit eget aliquet quis. Suspendisse eget egestas a elementum pulvinar et feugiat blandit at. In mi viverra elit nunc',
    selected: selectedItem.value === 0,
    image: 'https://images.unsplash.com/photo-1498758536662-35b82cd15e29?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2102&q=80'
  },
  {
    id: 1,
    name: 'Continuous Learning and Improvement',
    description: 'Quis tellus eget adipiscing convallis sit sit eget aliquet quis. Suspendisse eget egestas a elementum pulvinar et feugiat blandit at. In mi viverra elit nunc',
    selected: selectedItem.value === 1,
    image: 'https://images.unsplash.com/photo-1567532900872-f4e906cbf06a?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1280&q=80'
  },
  {
    id: 2,
    name: 'Customizable to your Brand',
    description: 'Quis tellus eget adipiscing convallis sit sit eget aliquet quis. Suspendisse eget egestas a elementum pulvinar et feugiat blandit at. In mi viverra elit nunc',
    selected: selectedItem.value === 2,
    image: 'https://images.unsplash.com/photo-1521737711867-e3b97375f902?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1587&q=80'
  },
  {
    id: 3,
    name: 'Transparent Analytics',
    description: 'Quis tellus eget adipiscing convallis sit sit eget aliquet quis. Suspendisse eget egestas a elementum pulvinar et feugiat blandit at. In mi viverra elit nunc',
    selected: selectedItem.value === 3,
    image: 'https://images.unsplash.com/photo-1520333789090-1afc82db536a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2102&q=80'
  }
]);

const selectedItem = ref(0);
const selectedImage = computed(() => items.value[selectedItem.value].image);

function onSelectItem(item) {
  selectedItem.value = item.id;
}
</script>

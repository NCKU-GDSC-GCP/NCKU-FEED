// 已登入
<script setup>
import { ref } from 'vue';
defineProps({
    myImg: String,
});

const isOpen = ref(false);
</script>

<template>
  <nav class="flex items-center justify-between flex-wrap bg-[#FF8E3C] p-4 lg:p-0 fixed top-0 inset-x-0 z-10">
    <div class="lg:flex items-center text-white mr-6 ml-4">
      <router-link to="/" class="flex items-center">
        <picture class="hidden lg:flex">
          <img src="../assets/nckufeed_white.svg" class="lg:h-20 lg:mx-2 lg:pl-8">
        </picture>
        <span class="font-mono font-black text-3xl tracking-tight">NCKU FEED</span>
      </router-link>
    </div>
    <div class="block lg:hidden mr-4">
      <button @click="isOpen = !isOpen" class="flex items-center px-3 py-2 border rounded text-white border-white hover:text-gray-300 hover:border-gray-300">
        <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0zm0 6h20v2H0zm0 6h20v2H0z"/></svg>
      </button>
    </div>

    <!-- lg留著如果之後有需要讓他們排列在navbar就可以用 -->
    <div :class="{'hidden': !isOpen}" class="w-full flex-grow lg:flex lg:items-center lg:w-auto lg:hidden">
      <div class="text-base lg:flex-grow ">
        <router-link to="/myUserPage" class="block mt-4 ml-4 lg:inline-block lg:mt-0 text-white hover:text-gray-300 mr-4">
            個人頁面
        </router-link>
        <router-link to="/" class="block mt-4 ml-4 lg:inline-block lg:mt-0 text-white hover:text-gray-300 mr-4">收藏清單</router-link>
      </div>
    </div>

    <div class="hidden lg:flex mx-12 items-center">
            <router-link to="/">
                <picture>
                   <img src="../assets/bookmark.png" class="h-6 lg:h-8 mx-3 lg:mx-4">
                </picture>
            </router-link>
            <router-link to="/myUserPage">
              <picture>
                <img :src="myImg" class="h-6 lg:h-8 mx-3 lg:mx-4 rounded-full">
             </picture>
            </router-link>
        </div>
  </nav>
</template>

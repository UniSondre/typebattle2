<template>
  <UApp :toaster="{position:'top-center', duration: 2000}" class="flex h-full w-full">
    <router-view class="flex-1 overflow-auto bg-[#2C2C2C] "></router-view>
  </UApp>
</template>
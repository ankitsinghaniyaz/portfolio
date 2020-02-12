<template>
  <div class="w-full h-full lg:flex">
    <div class="w-full h-full border border-grey-light bg-white rounded-b p-4 flex flex-col justify-between leading-normal">
      <div class="mb-8">
        <p class="text-grey-darkest text-base">
          {{ testimony.message }}
        </p>
      </div>
      <div class="flex items-center">
        <img class="w-10 h-10 rounded-full mr-4" :src="testimony.avatar" :alt="testimony.author">
        <div class="text-sm">
          <p class="text-black leading-none">{{ testimony.author }}</p>
          <p class="text-grey-dark">{{ testimony.role }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    testimony: Object
  }
};
</script>


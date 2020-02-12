<template>
  <div class="w-full h-full lg:flex">
    <div class="w-full h-full border border-grey-light bg-white rounded-b p-4 flex flex-col justify-between leading-normal">
      <div class="mb-8">
        <h3 class="mb-2">{{ blog.title }}</h3>
        <p class="text-grey-darkest text-base">
          {{ blog.excerpt }}
        </p>
      </div>
      <div class="flex items-center">
        <a class="bg-blue hover:bg-blue-dark text-white font-bold py-2 px-4 rounded no-underline" :href="blog.link" target="_blank">
          Read More
        </a>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  props: {
    blog: Object
  }
};
</script>

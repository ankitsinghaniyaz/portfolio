<template>
  <div class="w-full h-full lg:flex">
    <div
      class="border rounded border-grey-light bg-white p-4 flex flex-col justify-between leading-normal flex-auto h-full"
      :class="{'lg:rounded-r-none lg:border-r': !noPicture}"
    >
      <div class="flex flex-row">
        <div class="flex-1">
          <div class="mb-4">
            <div class="text-black font-bold text-2xl">{{ project.title }}</div>
            <p class="text-sm text-grey-darker flex items-center uppercase mb-4 mt-0">
              {{project.role}}
            </p>
            <p class="text-grey-darkest text-base">{{ project.description }}</p>
          </div>
          <div class="flex items-center mb-4">
            <img
              v-for="(logo, i) of project.icons"
              :key="`${project.title + i}`"
              class="w-8 h-8 rounded-full mr-4"
              :src="logo"
            >
          </div>
          <div class="flex items-center">
            <a
              :class="{'opacity-50 cursor-not-allowed': disabled}"
              class="bg-blue hover:bg-blue-dark text-white font-bold py-2 px-4 rounded no-underline"
              :href="project.link"
              target="_blank"
              :disabled="disabled"
            >{{ project.c2a }}</a>
          </div>
        </div>

        <div
          v-if="!noPicture"
          class="h-auto w-1/3 rounded-lg overflow-hidden border-grey-light ml-8 my-4 mr-4 border-2 hidden lg:flex"
        >
          <img :src="project.thumbnail" alt class="w-full h-full">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    project: Object,
    noPicture: Boolean
  },
  computed: {
    disabled() {
      return !this.project.link;
    }
  }
};
</script>


<template>
  <div v-editable="blok">
    <div class="relative">
      <div class="absolute inset-x-0 bottom-0 h-1/2" />
      <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
        <div class="relative shadow-xl sm:overflow-hidden">
          <div class="absolute inset-0">
            <SbImage
              v-if="blok.image"
              :src="blok.image"
              :classes="{picture: 'aspect-ratio-16/9', image:'object-cover h-full w-full' }"
              :resize="{ width: '1200', height: '0' }"
            />
            <div class="absolute inset-0 bg-yellow-200 mix-blend-multiply" />
          </div>
          <div class="relative px-4 py-16 sm:px-6 sm:py-24 lg:py-32 lg:px-8">
            <h1 class="text-center text-4xl font-extrabold tracking-tight sm:text-5xl lg:text-6xl">
              <span class="block text-white">We're Hiring</span>
              <span class="block text-yellow-200">Join us today!</span>
            </h1>
            <p class="mt-6 max-w-lg mx-auto text-center text-xl text-yellow-200 sm:max-w-3xl">
              We're looking for people to play! :)
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    blok: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>

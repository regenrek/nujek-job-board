<template>
  <NjSection
    variant="constrained"
    :fixed-classes="{ wrapper: 'pt-12 pb-24', container: 'max-w-3xl' }"
  >
    <nav aria-label="Back">
      <nuxt-link to="/" class="py-2 text-sm font-medium">
        Back to <b>Job Board</b>
      </nuxt-link>
    </nav>

    <div v-if="blok" class="py-12">
      <h1 class="text-3xl">
        {{ blok.content.title }}
      </h1>
      <SbRichtext class="mt-8" :text="blok.content.description" />

      <span class="block mt-4">
        <span class="inline-flex items-center px-2.5 py-0.5 rounded-md text-sm font-medium bg-red-100 text-red-800">
          💰 {{ blok.content.salary }} €
        </span>
      </span>

      <button type="button" class="mt-8 inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-full shadow-sm text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
        Apply now
      </button>
    </div>
  </NjSection>
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

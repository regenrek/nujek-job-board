<template>
  <NjSection
    variant="constrained"
    :fixed-classes="{ wrapper: 'pt-12 pb-24', container: 'max-w-3xl' }"
  >
    <div class="shadow overflow-hidden sm:rounded-md">
      <ul role="list" class="divide-y divide-gray-200">
        <SbQuery :posts-per-page-client-only="5" path="jobs" :filter-client-only="true">
          <template #default="story">
            <JobItem :title="story.content.title" :salary="story.content.salary" :link="story.full_slug" />
          </template>
        </SbQuery>
      </ul>
    </div>
    </div>
  </NjSection>
</template>

<script>
export default {
  props: {
    bloks: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>

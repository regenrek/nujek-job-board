<template>
  <Blok v-if="story.content" :blok="story" />
</template>
<script>
export default {
  async asyncData ({ $storyapi, error, route }) {
    try {
      const fullSlug = (route.path === '/' || route.path === '') ? 'home' : route.path

      const currentPage = await $storyapi.getStory(
        fullSlug,
        {
          resolve_links: 'url'
        }
      )

      return {
        story: currentPage.data.story
      }
    } catch (e) {
      error({
        statusCode: 404,
        message: e.message
      })
    }
  }
}
</script>

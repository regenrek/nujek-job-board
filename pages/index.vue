<template>
  <div>
    <Blok v-if="story.content" :blok="story.content" />
  </div>
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

      // alternative: if you plan to use nuxt-storyblok-queries
      // const { story } = await $storyblok.getCurrentStory({
      //   resolve_links: 'url',
      // })

      return {
        story: currentPage.data.story
      }
    } catch (e) {
      console.error('Exception', e)
      error({
        statusCode: 404,
        message: e.message
      })
    }
  }
}
</script>

<template>
  <div class="posts-page">
		<PostList />
  </div>
</template>

<script>
  import PostList from '~/components/Posts/PostPreview'

  export default {
    components: {
      PostList
    },

  }
</script>

<style scoped>

</style>

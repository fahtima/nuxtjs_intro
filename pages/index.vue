<template>
  <section class="container">
    <div>
      <logo />
      <h1 class="title">
KBlog Kidocode
</h1>
      <div class="links">
        <nuxt-link
          v-for="post in posts"
          :key="post.id"
          :to="{name: 'posts-id', params: {id: post.id}}"
          class="button--grey"
        >
{{ post.title }}
</nuxt-link>
      </div>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
export default {
  components: {
    Logo
  },
  head() {
    return {
      title: 'Home Page 🍕',
      meta: [
        { name: 'twitter:title', content: 'kblog kidocode by Kidocode' },
        { name: 'twitter:description', content: 'Nuxt + Vue School = 🍕' },
        {
          name: 'twitter:image',
          content:
            'https://s3-ap-southeast-1.amazonaws.com/kidocodeweb/assets/images/KIDOCODE_LOGO_2.svg'
        },
        { name: 'twitter:card', content: 'summary_large_image' }
      ]
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts.all
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  letter-spacing: 1px;
}
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
}
.links {
  padding-top: 15px;
}
</style>

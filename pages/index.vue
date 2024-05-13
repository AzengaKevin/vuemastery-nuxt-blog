<script setup lang="ts">
import type { Post } from '@/data/posts'
import { getPostsUrl } from '@/data/posts'

const { data: posts } = await useFetch<Post[]>(getPostsUrl())
</script>
<template>
  <main>
    <h1>Vuemastery Nuxt Blog</h1>
    <div>
      <PostCard v-for="post in posts" :key="post.id" :post="post" />
    </div>
  </main>
</template>

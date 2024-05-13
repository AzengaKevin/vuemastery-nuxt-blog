<script setup lang="ts">
import type { PostDetails } from '@/data/posts'
import { getPostDetailsUrl } from '@/data/posts'

const postSlug = useParam('post')

const { data: post } = await useFetch<PostDetails>(getPostDetailsUrl(postSlug))
</script>
<template>
  <main>
    <template v-if="post">
      <h1>{{ post?.title }}</h1>

      <CategoryLink :category="post?.category" />
      <RenderMarkdown :source="post?.content" />
    </template>
  </main>
</template>

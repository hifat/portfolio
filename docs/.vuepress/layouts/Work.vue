<script setup>
import { useBlogType } from '@vuepress/plugin-blog/client'
import ParentLayout from '@vuepress/theme-default/layouts/Layout.vue'
import ArticleList from '../components/ArticleList.vue'

const timelineworks = useBlogType('timelinework')
</script>

<template>
  <ParentLayout>
    <template #page>
      <main class="page">
        <h1 class="timelinework-title">timelinework</h1>
        <ArticleList :items="timelineworks.items" is-timelinework />
      </main>
    </template>
  </ParentLayout>
</template>

<style lang="scss">
.timelinework-title {
  padding-top: calc(var(--navbar-height) + 1rem) !important;
  text-align: center;
}
</style>

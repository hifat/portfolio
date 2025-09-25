<script setup>
import { useBlogType } from '@vuepress/plugin-blog/client'
import ParentLayout from '@vuepress/theme-default/layouts/Layout.vue'
import ArticleList from '../components/ArticleList.vue'

const works = useBlogType('work')
</script>

<template>
  <ParentLayout>
    <template #page>
      <main class="page">
        <h1 class="work-title">Work</h1>
        <ArticleList :items="works.items" is-work />
      </main>
    </template>
  </ParentLayout>
</template>

<style lang="scss">
.work-title {
  padding-top: calc(var(--navbar-height) + 1rem) !important;
  text-align: center;
}
</style>

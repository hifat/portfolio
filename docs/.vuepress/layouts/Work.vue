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
        <h3 class="txt-center">
          PERSONAL PROJECTS / INDEPENDENT DEVELOPMENT<br>
          2025 - present
        </h3>
        <ArticleList :items="works.items.filter((item) => item.info.type == 'personal-work')" is-work />

        <h3 class="txt-center">
          DEEPLOY TECHNOLOGY COMPANY <br>
          2022 - 2024
        </h3>
        <ArticleList :items="works.items.filter((item) => item.info.type == '')" is-work />
      </main>
    </template>
  </ParentLayout>
</template>

<style lang="scss">
.txt-center {
  text-align: center;
}

.work-title {
  padding-top: calc(var(--navbar-height) + 1rem) !important;
  text-align: center;
}
</style>

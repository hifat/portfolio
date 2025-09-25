<script setup>
import { withBase } from 'vuepress/client'

defineProps({
   /** Article items */
   items: {
      type: Array,
      required: true,
   },
   /** Whether is work or not */
   isWork: Boolean,
})
</script>

<template>
   <div class="article-wrapper">
      <div v-if="!items.length">Nothing in here.</div>
      <article v-for="{ info, path } in items.filter(item => item.info.type === 'personal-work')" :key="path" class="article" @click="$router.push(path)">
         <div class="article-content">
            <div class="article-img-wrapper">
               <img v-if="info.image" :src="withBase(info.image)" class="article-img" />
            </div>
            <div class="article-text">
               <header class="title">
                  {{ info.title }}
               </header>

               <hr />

               <div class="article-info">
                  <span v-if="info.author" class="author">Author: {{ info.author }}</span>
                  <span v-if="info.date && !isWork" class="date">Date: {{ new Date(info.date).toLocaleDateString() }}</span>
               </div>

               <div v-if="info.excerpt" class="excerpt" v-html="info.excerpt" />
            </div>
         </div>
      </article>
   </div>
</template>

<style lang="scss">
@use '@vuepress/theme-default/styles/mixins';

.article-img-wrapper {
   width: 100%;
   max-width: 120px;
   height: 170px;
   overflow: hidden;
   flex-shrink: 0;
   border-radius: 0.3rem;
}

.article-img {
   width: 100%;
   height: 100%;
   object-fit: cover;
   object-position: top;
}

.article-wrapper {
   @include mixins.content-wrapper;
   text-align: center;
}

.article {
   position: relative;

   box-sizing: border-box;
   width: 100%;
   margin: 0 auto 1.25rem;
   padding: 1rem 1.25rem;
   border: 1px solid var(--vp-c-border);
   border-radius: 0.4rem;

   .article-content {
      display: flex;
      gap: 1.25rem;
      align-items: flex-start;
   }

   .cover-image {
      width: 120px;
      height: 120px;
      object-fit: cover;
      border-radius: 0.3rem;
      flex-shrink: 0;
   }

   .article-text {
      flex: 1;
   }

   color: var(--vp-c-text);

   text-align: start;

   @media (max-width: 419px) {
      border-radius: 0;
   }

   &:hover {
      cursor: pointer;
   }

   .title {
      position: relative;
      display: inline-block;
      font-size: 1.28rem;
      line-height: 2rem;

      &::after {
         content: '';

         position: absolute;
         inset-inline-start: 0;
         bottom: 0;

         width: 100%;
         height: 2px;

         background: var(--vp-c-accent-bg);

         visibility: hidden;

         transition: transform var(--vp-t-transform);

         transform: scaleX(0);
      }

      &:hover::after {
         visibility: visible;
      }
   }

   .article-info {
      display: flex;
      flex-shrink: 0;

      > span {
         margin-inline-end: 0.5em;
         line-height: 1.8;
      }
   }

   .excerpt {
      h1 {
         display: none;
      }

      h2 {
         font-size: 1.2em;
      }

      h3 {
         font-size: 1.15em;
      }
   }
}
</style>

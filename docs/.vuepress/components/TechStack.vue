<script setup>
import { ref } from 'vue'

defineProps({
   stacks: {
      type: Array,
      required: true,
   },
})

const logoLinkSet = ref({
   go: 'https://icon.icepanel.io/Technology/svg/Go.svg',
   jenkins: 'https://icon.icepanel.io/Technology/svg/Jenkins.svg',
   sonarqube: 'https://icon.icepanel.io/Technology/svg/SonarQube.svg',
   argocd: 'https://icon.icepanel.io/Technology/svg/Argo-CD.svg',
   k8s: 'https://icon.icepanel.io/Technology/svg/Kubernetes.svg',
   mongodb: 'https://icon.icepanel.io/Technology/svg/MongoDB.svg',
   postgressql: 'https://icon.icepanel.io/Technology/svg/PostgresSQL.svg',
   oracle: 'https://icon.icepanel.io/Technology/svg/Oracle.svg',
   docker: 'https://icon.icepanel.io/Technology/svg/Docker.svg',
   'google-cloud': 'https://icon.icepanel.io/Technology/svg/Google-Cloud.svg',
   'gin-gonic': 'https://raw.githubusercontent.com/gin-gonic/logo/master/color.png',
   nodejs: "https://icon.icepanel.io/Technology/svg/Node.js.svg",
   nestjs: "https://icon.icepanel.io/Technology/svg/Nest.js.svg",
   strapi: "https://assets.super.so/e7c0f16c-8bd3-4c76-8075-4c86f986e1b2/uploads/favicon/9c68ae10-0a8a-4e3f-9084-3625b19df9cb.png",
   kibana: "https://icon.icepanel.io/Technology/svg/Kibana.svg",
   elasticsearch: "https://icon.icepanel.io/Technology/png-shadow-512/Elastic-Search.png",
   laravel: "https://icon.icepanel.io/Technology/svg/Laravel.svg",
   mysql: "https://icon.icepanel.io/Technology/svg/MySQL.svg",
   vue: "https://icon.icepanel.io/Technology/svg/Vue.js.svg",
   express: "https://icon.icepanel.io/Technology/png-shadow-512/Express.png",
   echo: "https://avatars.githubusercontent.com/u/2624634?s=48&v=4",
})
</script>

<template>
   <div>
      <span v-for="(stack, i) in stacks" :key="i" class="logo-stack">
         <img :src="logoLinkSet[stack]" :alt="stack" />
      </span>
   </div>
</template>

<style lang="scss">
.logo-stack {
   padding-left: 2px;
   padding-right: 2px;
}

.logo-stack img {
   height: 100%;
   max-height: 25px;
}
</style>

<template>
  <div class="antialiased text-slate-500 dark:text-slate-400 bg-c7o-night-rider">
    <!-- Google Tag Manager (noscript) -->
    <noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-TXCBS8HS" height="0" width="0" style="display: none; visibility: hidden"></iframe></noscript>
    <!-- End Google Tag Manager (noscript) -->
    <Home v-if="isIndex" />
    <!--<NotFound v-else-if="isNotFound" />-->
    <Blog v-else-if="isBlogHome" />
    <BusinessCases v-else-if="isResourcesHome" />
    <Product v-else-if="isProductHome" />
    <BlogLayout v-else-if="isBlogPage" />
    <DocLayout v-else-if="isDocPage" />
    <PageLayout v-else />
  </div>
</template>

<script setup>
import { computed, onMounted } from 'vue';
import { useRoute, useData } from 'vitepress';
import Home from './Home.vue';
import NotFound from './NotFound.vue';
import Blog from './Blog.vue';

import Product from './Product.vue';
import BusinessCases from './BusinessCases.vue';
import BlogLayout from './BlogLayout.vue';
import PageLayout from './PageLayout.vue';
import DocLayout from './DocLayout.vue';

const route = useRoute();
const { page, frontmatter } = useData();
const isIndex = computed(() => frontmatter.value.index);
// const isNotFound = computed(() => route.component === NotFound)
const isBlogHome = computed(() => frontmatter.value.isBlogHome);
const isResourcesHome = computed(() => frontmatter.value.isResourcesHome);
const isProductHome = computed(() => frontmatter.value.isProductHome);
const isBlogPage = computed(() => page.value.filePath.startsWith('blog/') || page.value.filePath.startsWith('resources/'));
const isDocPage = computed(() => page.value.filePath === 'subprocessors.md' || page.value.filePath === 'msa.md');

onMounted(() => {
  document.documentElement.classList.remove('dark');
});
</script>

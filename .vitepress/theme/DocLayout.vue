<template>
  <PageHeader></PageHeader>

  <div class="bg-c7o-strobe-light">
    <div class="w-full mx-auto max-w-4xl lg:flex">
      <Content class="prose prose-gray dark:prose-dark crescendo-blog-content" />
    </div>
  </div>
  <PageFooter></PageFooter>
</template>

<script>
import PageHeader from './PageHeader.vue';
import PageFooter from './PageFooter.vue';
import { ref, watch, computed } from 'vue';
import { useData, useRoute } from 'vitepress';

export default {
  data() {
    return {};
  },
  components: {
    PageHeader,
    PageFooter
  },
  setup() {
    const { site, page, theme, frontmatter: data } = useData();
    const route = useRoute();
    //const currentRoute = ref();
    return {
      theme,
      page,
      data: data,
      route: route
    };
  }
};
</script>

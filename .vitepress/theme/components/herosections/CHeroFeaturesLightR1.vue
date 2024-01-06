<template>
  <div id="whatwedo" class="bg-c7o-strobe-light py-24">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="mx-auto max-w-2xl lg:text-center">
        <p class="mt-2 text-6xl font-serif font-thin tracking-tight leading-tight text-gray-900">What We Do</p>
      </div>
      <div class="mx-auto mt-16 max-w-2xl sm:mt-20 lg:mt-24 lg:max-w-4xl">
        <dl class="grid max-w-xl grid-cols-1 gap-x-8 gap-y-10 lg:max-w-none lg:grid-cols-2 lg:gap-y-16">
          <div v-for="feature in items" :key="feature.name" class="relative pl-16">
            <dt class="text-xl font-semibold leading-7 text-gray-900">
              <div class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-c7o-purple-dark"><component :is="feature.icon" class="h-6 w-6 text-white" aria-hidden="true" /></div>
              {{ feature.name }}
            </dt>
            <dd class="mt-6 text-lg leading-7 text-gray-600">{{ feature.description }}</dd>
          </div>
        </dl>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive, computed } from 'vue';
import { ChartBarIcon, CpuChipIcon, ChatBubbleLeftIcon, CodeBracketIcon, Cog8ToothIcon, CloudArrowUpIcon } from '@heroicons/vue/24/outline';

const items = [
  {
    name: 'Generative AI',
    icon: CpuChipIcon,
    description: 'A fine balance of AI efficiency with human intelligence and empathy.',
    image: 'https://images.unsplash.com/photo-1498758536662-35b82cd15e29?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2102&q=80'
  },
  {
    name: 'Continuous Learning and Improvement',
    icon: CodeBracketIcon,
    description: 'Liberate agents from mundane tasks and empower them with meaningful work.',
    image: 'https://images.unsplash.com/photo-1567532900872-f4e906cbf06a?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1280&q=80'
  },
  {
    name: 'Efficient Deployment',
    icon: CloudArrowUpIcon,
    description: 'A significant advantage over traditional models that require infrastructure investment.',
    image: 'https://images.unsplash.com/photo-1521737711867-e3b97375f902?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1587&q=80'
  },

  {
    name: 'Customizable to your Brand',
    icon: Cog8ToothIcon,
    description: 'While AI-driven services offer personalization, they may lack the human touch Crescendo aims to provide.',
    image: 'https://images.unsplash.com/photo-1521737711867-e3b97375f902?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1587&q=80'
  },
  {
    name: 'Transparent, summarizable Analytics',
    icon: ChartBarIcon,
    description: 'A significant advantage over traditional models that require infrastructure investment.',
    image: 'https://images.unsplash.com/photo-1520333789090-1afc82db536a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2102&q=80'
  },
  {
    name: '100% coverage of CX interactions',
    icon: ChatBubbleLeftIcon,
    description: 'While AI-driven services offer personalization, they may lack the human touch Crescendo aims to provide.',
    image: 'https://images.unsplash.com/photo-1520333789090-1afc82db536a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2102&q=80'
  }
];
</script>

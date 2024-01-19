<template>
  <div id="whatwedo" class="bg-c7o-strobe-light py-10">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="mx-auto max-w-2xl lg:text-center">
        <p class="mt-2 text-6xl font-serif font-thin tracking-tight leading-tight text-gray-900">What We Do</p>
      </div>
      <div class="mx-auto mt-12 max-w-2xl lg:max-w-4xl">
        <dl class="grid max-w-xl grid-cols-1 gap-x-8 gap-y-8 lg:max-w-none lg:grid-cols-2 lg:gap-y-10">
          <div v-for="feature in items" :key="feature.name" class="relative pl-16">
            <dt class="text-xl font-semibold leading-7 text-gray-900">
              <div class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-c7o-purple-dark"><component :is="feature.icon" class="h-6 w-6 text-white" aria-hidden="true" /></div>
              {{ feature.name }}
            </dt>
            <div class="mt-6 text-lg leading-7 text-gray-600 max-w-xs">{{ feature.description }}</div>
          </div>
        </dl>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive, computed } from 'vue';
import { ChartBarIcon, ChartPieIcon, CursorArrowRaysIcon, CpuChipIcon, ChatBubbleLeftIcon, CodeBracketIcon, Cog8ToothIcon, CloudArrowUpIcon } from '@heroicons/vue/24/outline';

const items = [
  {
    name: 'Stand out with CX, in a snap',
    icon: ChartPieIcon,
    description: 'Leave everything to us. We’ll curate an innovative service experience that sets you apart.',
    image: 'https://images.unsplash.com/photo-1498758536662-35b82cd15e29?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2102&q=80'
  },
  {
    name: 'The best of both worlds',
    icon: CpuChipIcon,
    description: 'We find an elegant balance between cutting-edge AI and high-touch human service.',
    image: 'https://images.unsplash.com/photo-1498758536662-35b82cd15e29?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2102&q=80'
  },
  {
    name: 'Only pay for successful outcomes',
    icon: CursorArrowRaysIcon,
    description: 'Our advanced AI means that you can evaluate every interaction to see how well we did. Only pay when we succeed.',
    image: 'https://images.unsplash.com/photo-1567532900872-f4e906cbf06a?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1280&q=80'
  },
  {
    name: 'We invest in our teams',
    icon: Cog8ToothIcon,
    description: 'Agents that are treated well treat customers well. That’s why we invest significantly in our team and use advanced AI to help them do their jobs.',
    image: 'https://images.unsplash.com/photo-1521737711867-e3b97375f902?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1587&q=80'
  },
  {
    name: 'The most advanced AI',
    icon: CloudArrowUpIcon,
    description: 'We built Crescendo’s c7o.ai platform on the most advanced AI available. It’s an exclusive, patent-pending technology tailored to deliver consistently outstanding CX.',
    image: 'https://images.unsplash.com/photo-1521737711867-e3b97375f902?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1587&q=80'
  },
  {
    name: 'Keep your customer close',
    icon: ChartBarIcon,
    description: 'Crescendo is more than outsourcing. We deliver a CX dashboard, powered by customer interactions, that deliver insights and recommendations to improve your business performance.',
    image: 'https://images.unsplash.com/photo-1520333789090-1afc82db536a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2102&q=80'
  }
  /*
  {
    name: '100% coverage of CX interactions',
    icon: ChatBubbleLeftIcon,
    description: 'While AI-driven services offer personalization, they may lack the human touch Crescendo aims to provide.',
    image: 'https://images.unsplash.com/photo-1520333789090-1afc82db536a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2102&q=80'
  }*/
];
</script>

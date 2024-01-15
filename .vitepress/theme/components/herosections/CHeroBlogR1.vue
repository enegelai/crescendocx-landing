<template>
  <div class="relative isolate overflow-hidden bg-c7o-night-rider py-10">
    <div class="mx-auto max-w-7xl px-6 pb-4 pt-4">
      <div class="flex justify-between items-center">
        <h2 class="text-3xl font-serif font-thin tracking-tight text-white sm:text-4xl">Latest updates</h2>
        <a href="/blog/" class="text-xl hover:underline text-white">Read more</a>
      </div>
      <div class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-x-8 gap-y-20 lg:mx-0 lg:max-w-none lg:grid-cols-3">
        <article v-for="(post, idx) in posts" :key="idx" class="flex flex-col items-start">
          <div class="relative w-full">
            <a :href="post.url">
              <img :src="post.frontmatter.image" alt="" class="aspect-[16/9] w-full bg-gray-100 object-cover sm:aspect-[2/1] lg:aspect-[3/2]" />
            </a>
          </div>
          <div class="max-w-xl">
            <div class="mt-4 flex items-center gap-x-4 text-sm">
              <time :datetime="post.date.time" class="text-gray-300">{{ post.date.string }}</time>
            </div>
            <dl class="py-4">
              <dt class="sr-only">Authors</dt>
              <dd>
                <ul class="flex xl:block space-x-8 sm:space-x-12 xl:space-x-0 xl:space-y-8">
                  <li class="flex items-center space-x-2 text-gray-400 hover:text-white">
                    <img v-if="post.frontmatter.avatar" :src="'/img/' + post.frontmatter.avatar" alt="author image" class="w-12 h-12 rounded-full" />
                    <img v-else :src="'/logo.png'" alt="logo image" class="w-12 h-12" />
                    <dl class="text-sm font-medium leading-5 whitespace-nowrap">
                      <dt class="sr-only">Name</dt>
                      <dd class="text-lg">
                        <a
                          :href="post.frontmatter.linkedin ? 'https://www.linkedin.com/in/' + post.frontmatter.linkedin : 'https://www.linkedin.com/company/enegel-ai'"
                          target="_blank"
                          rel="noopnener noreferrer"
                          class="link"
                          >{{ post.frontmatter.author ? post.frontmatter.author : 'Enegel.ai' }}</a
                        >
                      </dd>
                      <dt class="sr-only">LinkedIn</dt>
                      <dd>
                        <a
                          :href="post.frontmatter.linkedin ? 'https://www.linkedin.com/in/' + post.frontmatter.linkedin : 'https://www.linkedin.com/company/enegel-ai'"
                          target="_blank"
                          rel="noopnener noreferrer"
                          class="text-slate-700 hover:text-slate-900 dark:text-slate-400 dark:hover:text-white link"
                          ><img class="w-6 h-6" :src="'/img/icons8-linkedin-96-purple.svg'"
                        /></a>
                      </dd>
                    </dl>
                  </li>
                </ul>
              </dd>
            </dl>
            <div class="group relative">
              <h3 class="mt-3 text-lg font-semibold leading-6 text-gray-300 group-hover:text-white">
                <a :href="post.url">
                  <span class="absolute inset-0" />
                  {{ post.title }}
                </a>
              </h3>
              <div class="mt-5 text-md leading-6 text-gray-400" v-html="post.excerpt"></div>
            </div>
            <!--<div class="relative mt-8 flex items-center gap-x-4">
              <img :src="post.author.imageUrl" alt="" class="h-10 w-10 rounded-full bg-gray-100" />
              <div class="text-sm leading-6">
                <p class="font-semibold text-gray-900">
                  <a :href="post.author.href">
                    <span class="absolute inset-0" />
                    {{ post.author.name }}
                  </a>
                </p>
                <p class="text-gray-600">{{ post.author.role }}</p>
              </div>
            </div>-->
          </div>
        </article>
      </div>
    </div>
  </div>
</template>

<script setup>
import { data as allPosts } from '../../posts.data';
const posts = allPosts.slice(0, 3);
const posts2 = [
  {
    id: 1,
    title: 'Boost your conversion rate',
    href: '#',
    description:
      'Illo sint voluptas. Error voluptates culpa eligendi. Hic vel totam vitae illo. Non aliquid explicabo necessitatibus unde. Sed exercitationem placeat consectetur nulla deserunt vel. Iusto corrupti dicta.',
    imageUrl: 'https://images.unsplash.com/photo-1496128858413-b36217c2ce36?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=3603&q=80',
    date: 'Mar 16, 2020',
    datetime: '2020-03-16',
    category: { title: 'Marketing', href: '#' },
    author: {
      name: 'Michael Foster',
      role: 'Co-Founder / CTO',
      href: '#',
      imageUrl: 'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'
    }
  }
  // More posts...
];
console.log(`Posts:`, posts);
</script>

<script setup>
import Date from './Date.vue';
import PageHeader from './PageHeader.vue';
import PageFooter from './PageFooter.vue';
import { data as posts } from './posts.data';
</script>

<template>
  <PageHeader></PageHeader>
  <div class="antialiased bg-c7o-strobe-light pb-20">
    <header class="pt-8 pb-4 lg:pt-16 lg:pb-6 text-center">
      <h1 class="mb-4 text-3xl sm:text-4xl tracking-tight font-serif text-slate-900 font-light dark:text-slate-200">Latest Updates</h1>
    </header>
    <main class="max-w-3xl mx-auto px-4 sm:px-6 xl:max-w-5xl xl:px-0">
      <div class="mt-10 space-y-20">
        <article v-for="post in posts" :key="post.id" class="relative isolate flex flex-col gap-8 lg:flex-row">
          <a :href="post.url">
            <div class="relative aspect-[16/9] sm:aspect-[2/1] lg:aspect-square lg:w-64 lg:shrink-0">
              <img :src="post.frontmatter.image" alt="" class="absolute inset-0 h-full w-full bg-gray-50 object-cover" />
              <div class="absolute inset-0 rounded-2xl ring-1 ring-inset ring-gray-900/10" />
            </div>
          </a>
          <div>
            <div class="flex items-center gap-x-4 text-sm">
              <time :datetime="post.date.time" class="text-gray-500">{{ post.date.string }}</time>
            </div>
            <div class="group relative max-w-xl">
              <h3 class="mt-3 text-xl font-semibold leading-6 text-gray-600 group-hover:text-black">
                <a :href="post.url">
                  <span class="absolute inset-0" />
                  {{ post.title }}
                </a>
              </h3>
              <p class="mt-5 text-md leading-6 text-gray-600" v-html="post.excerpt"></p>
            </div>
            <dl class="py-4">
              <dt class="sr-only">Authors</dt>
              <dd>
                <ul class="flex xl:block space-x-8 sm:space-x-12 xl:space-x-0 xl:space-y-8">
                  <li class="flex items-center space-x-2 text-gray-600 hover:text-black">
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

            <!--<div class="mt-6 flex border-t border-gray-900/5 pt-6">
              <div class="relative flex items-center gap-x-4">
                <img :src="post.author.imageUrl" alt="" class="h-10 w-10 rounded-full bg-gray-50" />
                <div class="text-sm leading-6">
                  <p class="font-semibold text-gray-900">
                    <a :href="post.author.href">
                      <span class="absolute inset-0" />
                      {{ post.author.name }}
                    </a>
                  </p>
                  <p class="text-gray-600">{{ post.author.role }}</p>
                </div>
              </div>
            </div>-->
          </div>
        </article>
      </div>

      <!--<div class="relative sm:pb-12 sm:ml-[calc(2rem+1px)] md:ml-[calc(3.5rem+1px)] lg:ml-[max(calc(14.5rem+1px),calc(100%-48rem))]">
        <div class="hidden absolute top-3 bottom-0 right-full mr-7 md:mr-[3.25rem] w-px bg-slate-200 dark:bg-slate-800 sm:block"></div>
        <div class="space-y-16">
          <article class="relative group" v-for="{ title, url, date, excerpt } of posts">
            <div class="absolute -inset-y-2.5 -inset-x-4 md:-inset-y-4 md:-inset-x-6 sm:rounded-2xl group-hover:bg-slate-50/70 dark:group-hover:bg-slate-800/50"></div>
            <svg viewBox="0 0 9 9" class="hidden absolute right-full mr-6 top-2 text-slate-200 dark:text-slate-600 md:mr-12 w-[calc(0.5rem+1px)] h-[calc(0.5rem+1px)] overflow-visible sm:block">
              <circle cx="4.5" cy="4.5" r="4.5" stroke="currentColor" class="fill-white dark:fill-slate-900" stroke-width="2"></circle>
            </svg>
            <div class="relative">
              <h1 class="text-2xl font-semibold tracking-tight text-slate-900 dark:text-slate-200 pt-8 lg:pt-0">
                {{ title }}
              </h1>
              <div class="mt-2 mb-4 prose prose-slate prose-a:relative prose-a:z-10 dark:prose-dark line-clamp-3">
                <div v-if="excerpt" class="" v-html="excerpt"></div>
              </div>
              <dl class="absolute left-0 top-0 lg:left-auto lg:right-full lg:mr-[calc(6.5rem+1px)]">
                <dt class="sr-only">Date</dt>
                <dd class="whitespace-nowrap text-sm leading-6 dark:text-slate-400">
                  <Date :date="date" />
                </dd>
              </dl>
            </div>
            <a class="flex items-center text-sm text-sky-500 font-medium" :href="url"
              ><span class="absolute -inset-y-2.5 -inset-x-4 md:-inset-y-4 md:-inset-x-6 sm:rounded-2xl"></span
              ><span class="relative"
                >Read more<span class="sr-only">, {{ title }}</span></span
              ><svg
                class="relative mt-px overflow-visible ml-2.5 text-sky-300 dark:text-sky-700"
                width="3"
                height="6"
                viewBox="0 0 3 6"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path d="M0 0L3 3L0 6"></path></svg
            ></a>
          </article>
        </div>
      </div>-->
    </main>
  </div>
  <PageFooter></PageFooter>
</template>

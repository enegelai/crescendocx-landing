<template>
  <header class="sticky top-0 z-40 w-full backdrop-blur flex-none transition-colors duration-500 lg:z-50 border-b border-c7o-purple/50 supports-backdrop-blur:bg-c7o-night-rider/80">
    <nav class="mx-auto flex max-w-7xl items-center justify-between p-4 lg:px-8" aria-label="Global">
      <div class="flex lg:flex-1">
        <a href="/" class="-m-1.5 p-1.5">
          <span class="sr-only">Crescendo</span>
          <LogoGradient class="text-white w-full h-6"></LogoGradient>
        </a>
      </div>
      <div class="flex lg:hidden">
        <button type="button" class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700" @click="mobileMenuOpen = true">
          <span class="sr-only">Open main menu</span>
          <Bars3Icon class="h-6 w-6 cursor-pointer" aria-hidden="true" />
        </button>
      </div>
      <div class="hidden lg:flex items-center">
        <!--<a href="/blog/" class="mr-4 text-sm font-semibold leading-6 text-gray-100">Blog</a>-->
        <div class="hidden lg:flex lg:flex-1 lg:justify-end">
          <a href="/company/sayhello" class="text-sm font-semibold leading-6 bg-c7o-strobe hover:bg-c7o-strobe-hover px-4 py-2 rounded-3xl text-black">Say hello</a>
        </div>
      </div>
    </nav>
    <ClientOnly>
      <Dialog as="div" class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
        <!--<div class="fixed inset-0 z-10" />-->
        <DialogPanel class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-c7o-night-rider px-4 py-4 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
          <div class="flex items-center justify-between">
            <div class="flex lg:flex-1">
              <a href="/" class="-m-1.5 p-1.5">
                <span class="sr-only">Crescendo</span>
                <LogoGradient class="text-slate-900 dark:text-slate-900 w-auto h-6"></LogoGradient>
              </a>
            </div>
            <div class="flex lg:hidden">
              <button type="button" class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700" @click="mobileMenuOpen = false">
                <span class="sr-only">Close main menu</span>
                <XMarkIcon class="h-6 w-6" aria-hidden="true" />
              </button>
            </div>
          </div>
          <div class="mt-12 flow-root">
            <div class="-my-6 divide-y divide-gray-500/10">
              <div class="space-y-2 py-2">
                <a href="/blog/" class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-100 hover:bg-gray-800">Blog</a>
              </div>
              <div class="py-2">
                <a href="/company/sayhello" class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-100 hover:bg-gray-800">Say hello</a>
              </div>
            </div>
          </div>
        </DialogPanel>
      </Dialog>
    </ClientOnly>
  </header>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import DarkModeSwitch from './components/DarkModeSwitch.vue';
import Logo from './components/Logo.vue';
import LogoCXAI from './components/LogoCXAI.vue';
import LogoGradient from './components/LogoGradient.vue';
import { Dialog, DialogPanel, Disclosure, DisclosureButton, DisclosurePanel, Popover, PopoverButton, PopoverGroup, PopoverPanel } from '@headlessui/vue';
import { ArrowPathIcon, Bars3Icon, ChartPieIcon, CursorArrowRaysIcon, FingerPrintIcon, SquaresPlusIcon, XMarkIcon, CheckCircleIcon, InformationCircleIcon } from '@heroicons/vue/24/outline';
import { ChevronDownIcon, PhoneIcon, PlayCircleIcon } from '@heroicons/vue/20/solid';

const products = [
  {
    name: 'Conversation Intelligence Dashboard',
    description: 'A cutting-edge solution designed to streamline call center operations and enhance agent performance',
    href: '/product/#conversation-intelligence-dashboard',
    icon: ChartPieIcon
  },
  {
    name: 'Personal Coach',
    description: 'Personal Coach utilizes advanced Generative AI technology, designed to analyze, optimize, and track agent performance over time. ',
    href: '/product/#personal-coach',
    icon: CursorArrowRaysIcon
  },
  {
    name: 'Bot Tester',
    description: 'The Enegel Bot Tester is a cutting-edge solution for evaluating and enhancing the performance of your Voice Bots and Chat Bots.',
    href: '/product/#bot-tester',
    icon: CheckCircleIcon
  }
];
const callsToAction = [
  { name: 'Learn More', href: '/product/', icon: InformationCircleIcon, class: 'bg-gray-50 text-gray-900 hover:bg-gray-100' },
  { name: 'Private Beta Waitlist', href: '/company/beta', icon: CursorArrowRaysIcon, class: 'bg-orange-600 text-white hover:bg-orange-500' }
];

const mobileMenuOpen = ref(false);

onMounted(() => {
  //document.documentElement.classList.remove('dark');
});
</script>

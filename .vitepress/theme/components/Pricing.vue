<template>
  <div class="bg-white">
    <main>
      <!-- Pricing section -->
      <div class="mx-auto max-w-7xl px-6 lg:px-8 py-16">
        <div class="mx-auto max-w-4xl text-center">
          <h1 class="text-base font-semibold leading-7 text-indigo-600">Pricing</h1>
          <p class="mt-2 text-4xl font-bold tracking-tight text-gray-900 sm:text-5xl">Pricing plans for teams of&nbsp;all&nbsp;sizes</p>
        </div>
        <p class="mx-auto mt-6 max-w-2xl text-center text-lg leading-8 text-gray-600">Choose an affordable plan with the best features for your business.</p>
        <div class="mt-16 flex justify-center">
          <RadioGroup v-model="frequency" class="grid grid-cols-2 gap-x-1 rounded-full p-1 text-center text-xs font-semibold leading-5 ring-1 ring-inset ring-gray-200">
            <RadioGroupLabel class="sr-only">Payment frequency</RadioGroupLabel>
            <RadioGroupOption as="template" v-for="option in pricing.frequencies" :key="option.value" :value="option" v-slot="{ checked }">
              <div :class="[checked ? 'bg-indigo-600 text-white' : 'text-gray-500', 'cursor-pointer rounded-full px-2.5 py-1']">
                <span>{{ option.label }}</span>
              </div>
            </RadioGroupOption>
          </RadioGroup>
        </div>
        <div class="isolate mx-auto mt-10 grid max-w-md grid-cols-1 gap-8 md:max-w-2xl md:grid-cols-2 lg:max-w-4xl xl:mx-0 xl:max-w-none">
          <div v-for="tier in pricing.tiers" :key="tier.id" :class="[tier.mostPopular ? 'ring-2 ring-indigo-600' : 'ring-1 ring-gray-200', 'rounded-3xl p-8']">
            <h2 :id="tier.id" :class="[tier.mostPopular ? 'text-indigo-600' : 'text-gray-900', 'text-lg font-semibold leading-8']">{{ tier.name }}</h2>
            <p class="mt-4 text-sm leading-6 text-gray-600">{{ tier.description }}</p>
            <p class="mt-6 flex items-baseline gap-x-1">
              <span class="text-4xl font-bold tracking-tight text-gray-900">{{ tier.price[frequency.value] }}</span>
              <span class="text-sm font-semibold leading-6 text-gray-600">{{ frequency.priceSuffix }}</span>
            </p>
            <a
              :href="tier.href"
              :aria-describedby="tier.id"
              :class="[
                tier.mostPopular ? 'bg-indigo-600 text-white shadow-sm hover:bg-indigo-500' : 'text-indigo-600 ring-1 ring-inset ring-indigo-200 hover:ring-indigo-300',
                'mt-6 block rounded-md py-2 px-3 text-center text-sm font-semibold leading-6 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600'
              ]"
            >
              {{ tier.button }}</a
            >
            <ul role="list" class="mt-8 space-y-3 text-sm leading-6 text-gray-600">
              <li v-for="feature in tier.features" :key="feature" class="flex gap-x-3">
                <CheckIcon class="h-6 w-5 flex-none text-indigo-600" aria-hidden="true" />
                {{ feature }}
              </li>
            </ul>
          </div>
        </div>
      </div>

      <!-- Logo cloud -->
      <!--
      <div class="mx-auto my-24 max-w-7xl px-6 sm:my-56 lg:px-8"></div>
        <div class="mx-auto mt-24 max-w-7xl px-6 sm:mt-32 lg:px-8">
          <div class="mx-auto grid max-w-lg grid-cols-4 items-center gap-x-8 gap-y-12 sm:max-w-xl sm:grid-cols-6 sm:gap-x-10 sm:gap-y-14 lg:mx-0 lg:max-w-none lg:grid-cols-5">
            <img class="col-span-2 max-h-12 w-full object-contain lg:col-span-1" src="https://tailwindui.com/img/logos/158x48/transistor-logo-gray-900.svg" alt="Transistor" width="158" height="48" />
            <img class="col-span-2 max-h-12 w-full object-contain lg:col-span-1" src="https://tailwindui.com/img/logos/158x48/reform-logo-gray-900.svg" alt="Reform" width="158" height="48" />
            <img class="col-span-2 max-h-12 w-full object-contain lg:col-span-1" src="https://tailwindui.com/img/logos/158x48/tuple-logo-gray-900.svg" alt="Tuple" width="158" height="48" />
            <img class="col-span-2 max-h-12 w-full object-contain sm:col-start-2 lg:col-span-1" src="https://tailwindui.com/img/logos/158x48/savvycal-logo-gray-900.svg" alt="SavvyCal" width="158" height="48" />
            <img class="col-span-2 col-start-2 max-h-12 w-full object-contain sm:col-start-auto lg:col-span-1" src="https://tailwindui.com/img/logos/158x48/statamic-logo-gray-900.svg" alt="Statamic" width="158" height="48" />
          </div>
          <div class="mt-16 flex justify-center">
            <p class="relative rounded-full bg-gray-50 px-4 py-1.5 text-sm leading-6 text-gray-600 ring-1 ring-inset ring-gray-900/5">
              <span class="hidden md:inline">Transistor saves up to $40,000 per year, per employee by working with us.</span>
              <a href="#" class="font-semibold text-indigo-600"><span class="absolute inset-0" aria-hidden="true" /> See our case study <span aria-hidden="true">&rarr;</span></a>
            </p>
          </div>
        </div>
        -->

      <!-- Testimonial section -->
      <!--
        <div class="mx-auto mt-24 max-w-7xl sm:mt-56 sm:px-6 lg:px-8">
          <div class="relative overflow-hidden bg-gray-900 px-6 py-20 shadow-xl sm:rounded-3xl sm:px-10 sm:py-24 md:px-12 lg:px-20">
            <img class="absolute inset-0 h-full w-full object-cover brightness-150 saturate-0" src="https://images.unsplash.com/photo-1601381718415-a05fb0a261f3?ixid=MXwxMjA3fDB8MHxwcm9maWxlLXBhZ2V8ODl8fHxlbnwwfHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1216&q=80" alt="" />
            <div class="absolute inset-0 bg-gray-900/90 mix-blend-multiply" />
            <div class="absolute -left-80 -top-56 transform-gpu blur-3xl" aria-hidden="true">
              <div class="aspect-[1097/845] w-[68.5625rem] bg-gradient-to-r from-[#ff4694] to-[#776fff] opacity-[0.45]" style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)" />
            </div>
            <div class="hidden md:absolute md:bottom-16 md:left-[50rem] md:block md:transform-gpu md:blur-3xl" aria-hidden="true">
              <div class="aspect-[1097/845] w-[68.5625rem] bg-gradient-to-r from-[#ff4694] to-[#776fff] opacity-25" style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)" />
            </div>
            <div class="relative mx-auto max-w-2xl lg:mx-0">
              <img class="h-12 w-auto" src="https://tailwindui.com/img/logos/workcation-logo-white.svg" alt="" />
              <figure>
                <blockquote class="mt-6 text-lg font-semibold text-white sm:text-xl sm:leading-8">
                  <p>“Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo expedita voluptas culpa sapiente alias molestiae. Numquam corrupti in laborum sed rerum et corporis.”</p>
                </blockquote>
                <figcaption class="mt-6 text-base text-white">
                  <div class="font-semibold">Judith Black</div>
                  <div class="mt-1">CEO of Workcation</div>
                </figcaption>
              </figure>
            </div>
          </div>
        </div>
        -->

      <!-- FAQ section -->
      <!--
        <div class="mx-auto my-24 max-w-7xl px-6 sm:my-56 lg:px-8">
          <div class="mx-auto max-w-4xl divide-y divide-gray-900/10">
            <h2 class="text-2xl font-bold leading-10 tracking-tight text-gray-900">Frequently asked questions</h2>
            <dl class="mt-10 space-y-6 divide-y divide-gray-900/10">
              <Disclosure as="div" v-for="faq in faqs" :key="faq.question" class="pt-6" v-slot="{ open }">
                <dt>
                  <DisclosureButton class="flex w-full items-start justify-between text-left text-gray-900">
                    <span class="text-base font-semibold leading-7">{{ faq.question }}</span>
                    <span class="ml-6 flex h-7 items-center">
                      <PlusSmallIcon v-if="!open" class="h-6 w-6" aria-hidden="true" />
                      <MinusSmallIcon v-else class="h-6 w-6" aria-hidden="true" />
                    </span>
                  </DisclosureButton>
                </dt>
                <DisclosurePanel as="dd" class="mt-2 pr-12">
                  <p class="text-base leading-7 text-gray-600">{{ faq.answer }}</p>
                </DisclosurePanel>
              </Disclosure>
            </dl>
          </div>
        </div>
        -->
    </main>
  </div>
</template>

<script setup>
import { defineComponent, h, ref } from 'vue';
import { Dialog, DialogPanel, Disclosure, DisclosureButton, DisclosurePanel, RadioGroup, RadioGroupLabel, RadioGroupOption } from '@headlessui/vue';
import { Bars3Icon, MinusSmallIcon, PlusSmallIcon, XMarkIcon } from '@heroicons/vue/24/outline';
import { CheckIcon } from '@heroicons/vue/20/solid';

const pricing = {
  frequencies: [
    { value: 'monthly', label: 'Monthly', priceSuffix: '/month' },
    { value: 'annually', label: 'Annually', priceSuffix: '/year' }
  ],
  tiers: [
    {
      name: 'Pay as you go',
      id: 'tier-startup',
      //href: 'https://checkout.stripe.com/c/pay/cs_test_a1NZksJmtH4mdfNo0mZclNZ9zDX2kuwYMJB6WmNM26PyLD7VXaElTxvBcZ#fidkdWxOYHwnPyd1blpxYHZxWjA0SzYwSFxNR05UZkN%2FQVZ%2FNWpQV39obl9SQ1RLXTM9c1BPZkZKTDRURnJUZD1CM2dsbElsMEpDS1NtbWNBbGtGPG5ScTwwbmI1UmJdXGA8amR8MXB0amZCNTVNM2x3d0ZIRCcpJ3VpbGtuQH11anZgYUxhJz8ncWB2cVowbkQycFFhYz1kTWIwalxgUFAneCUl',
      href: 'mailto:info@enegel.com',
      price: { monthly: '$99', annually: '$999' },
      description: 'A plan that scales with your rapidly growing business.',
      //button: "Buy plan",
      button: 'Contact sales',
      features: [
        'Summarization',
        'KPIs',
        'Individual Performance Analysis',
        'Team Performance Analysis',
        '100,000 words of analysis',
        '1 Gb data storage',
        'Online customer support',
        'Additional 10,000 words of analysis $10',
        'Analytics Data Storage $10/GB/Month',
        'Voice Transcription $0.009/minute'
      ],
      mostPopular: true
    },
    {
      name: 'Enterprise',
      id: 'tier-enterprise',
      href: 'mailto:info@enegel.com',
      price: { monthly: 'Contact us', annually: 'Contact us' },
      description: 'Dedicated support and infrastructure for your company.',
      button: 'Contact sales',
      features: [
        'Summarization',
        'KPIs',
        'Individual Performance Analysis',
        'Team Performance Analysis',
        '100,000 words of analysis',
        'Online customer support',
        'Additional 10,000 words of analysis $10',
        'Analytics Data Storage $10/GB/Month',
        'Voice Transcription $0.009/minute',
        'Dedicated support',
        'Unlimited CX analysis units',
        'Unlimited storage'
      ],
      mostPopular: false
    }
  ]
};
const faqs = [
  {
    question: "What's the best thing about Switzerland?",
    answer: "I don't know, but the flag is a big plus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas cupiditate laboriosam fugiat."
  }
  // More questions...
];

const mobileMenuOpen = ref(false);
const frequency = ref(pricing.frequencies[0]);
</script>

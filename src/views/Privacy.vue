<template>
  <div class="bg-white pt-16 sm-pt-8" id="header">
    <div class="max-w-7xl mx-auto py-12 px-4 sm:py-16 sm:px-6 lg:px-8">
      <div class="max-w-3xl mx-auto divide-y-2 divide-gray-200">
        <h2 class="text-center text-3xl font-extrabold sm:text-4xl">{{ $t("privacy.title") }}</h2>
        <dl class="mt-12 space-y-6 divide-y divide-gray-200">
          <Disclosure as="div" v-for="tier in privacy.tiers" :key="tier.title" class="pt-6" v-slot="{ open }">
            <dt class="text-lg">
              <DisclosureButton class="text-left w-full flex justify-between items-start text-gray-400">
                <span class="font-medium">
                  {{ tier.title }}
                </span>
                <span class="ml-6 h-7 flex items-center">
                  <ChevronDownIcon :class="[open ? '-rotate-180' : 'rotate-0', 'h-6 w-6 transform']" aria-hidden="true" />
                </span>
              </DisclosureButton>
            </dt>
            <DisclosurePanel as="dd" class="mt-2 pr-12">
              <p class="text-base">
                {{ tier.description }}
              </p>
              <ul role="list" class="mt-6 space-y-6">
                <li v-for="feature in tier.features" :key="feature" class="flex">
                  <ChevronRightIcon class="flex-shrink-0 w-6 h-6 text-rose-500" aria-hidden="true" />
                  <span class="ml-3 text-gray-500">{{ feature }}</span>
                </li>
              </ul>
            </DisclosurePanel>
          </Disclosure>
        </dl>
      </div>
    </div>
  </div>
</template>

<script>
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'
import { ChevronDownIcon, ChevronRightIcon } from '@heroicons/vue/outline'

export default {
  components: {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
    ChevronDownIcon,
    ChevronRightIcon
  },

  computed:{
    privacy(){

      return {
        tiers: [
          {
            title: this.$t('privacy.sub1'),
            description: 'Introduction :',
            features: [
              this.$t('privacy.cond1'),
              this.$t('privacy.cond2'),
            ],

          },
          {
            title: this.$t('privacy.sub2'),
            description: this.$t('privacy.hed2'),
          },
          {
            title: this.$t('privacy.sub3'),
            description: this.$t('privacy.hed3'),
            features: [
              this.$t('privacy.cond3'),
              this.$t('privacy.cond4'),
              this.$t('privacy.cond5'),
              this.$t('privacy.cond6'),
              this.$t('privacy.cond7'),
              this.$t('privacy.cond8'),
              this.$t('privacy.cond9'),
              this.$t('privacy.cond10'),
              this.$t('privacy.cond11'),
              this.$t('privacy.cond12'),
              this.$t('privacy.cond13'),
              this.$t('privacy.cond14'),
            ],
          },
          {
            title: this.$t('privacy.sub4'),
            description: this.$t('privacy.hed4'),
            features: [
              this.$t('privacy.cond15'),
              this.$t('privacy.cond16'),
              this.$t('privacy.cond17'),
              this.$t('privacy.cond18'),
              this.$t('privacy.cond19'),
              this.$t('privacy.cond20'),
              this.$t('privacy.cond21'),
              this.$t('privacy.cond22'),
              this.$t('privacy.cond23'),
              this.$t('privacy.cond24'),
              this.$t('privacy.cond25'),
              this.$t('privacy.cond26'),
              this.$t('privacy.cond27'),
              this.$t('privacy.cond28'),
              this.$t('privacy.cond29'),
              this.$t('privacy.cond30'),

            ],
          },
          {
            title: this.$t('privacy.sub5'),
            description: this.$t('privacy.hed5'),
            features: [
              this.$t('privacy.cond31'),
              this.$t('privacy.cond32'),
              this.$t('privacy.cond33'),
              this.$t('privacy.cond34'),
              this.$t('privacy.cond35'),
              this.$t('privacy.cond36'),
            ],
          },
          {
            title: this.$t('privacy.sub6'),
            description: this.$t('privacy.hed6'),
            features: [
              this.$t('privacy.cond37'),
              this.$t('privacy.cond38'),
              this.$t('privacy.cond39'),
            ],
          },
          {
            title: this.$t('privacy.sub7'),
            description: this.$t('privacy.hed7'),
            features: [
              this.$t('privacy.cond40'),
              this.$t('privacy.cond41'),
              this.$t('privacy.cond42'),
            ],
          },
          {
            title: this.$t('privacy.sub8'),
            description: this.$t('privacy.hed8'),
            features: [
              this.$t('privacy.cond43'),
              this.$t('privacy.cond44'),
              this.$t('privacy.cond45'),
              this.$t('privacy.cond46'),
            ],
          },
          {
            title: this.$t('privacy.sub9'),
            description: this.$t('privacy.hed9'),
          },
          {
            title: this.$t('privacy.sub10'),
            description: this.$t('privacy.hed10'),
            features: [
              this.$t('privacy.cond47'),
              this.$t('privacy.cond48'),
              this.$t('privacy.cond49'),
              this.$t('privacy.cond50'),
              this.$t('privacy.cond51'),
            ],
          },
          {
            title: this.$t('privacy.sub11'),
            description: this.$t('privacy.hed11'),
          },
          {
            title: this.$t('privacy.sub12'),
            description: this.$t('privacy.hed12'),
          },
          {
            title: this.$t('privacy.sub13'),
            description: this.$t('privacy.hed13'),
            features: [
              this.$t('privacy.cond52'),
              this.$t('privacy.cond53'),
              this.$t('privacy.cond54'),
              this.$t('privacy.cond55'),
              this.$t('privacy.cond56'),
            ],
          },
          {
            title: this.$t('privacy.sub14'),
            description: this.$t('privacy.hed14'),
          },
        ],
      }

    },

  }
}
</script>
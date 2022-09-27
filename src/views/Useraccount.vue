<template>

  <header>
    <div class="bg-white">
      <div class="max-w-7xl mx-auto pt-16 pb-10 px-4 sm:pt-24 sm:pb-10 sm:px-6 lg:px-8">
        <div class="text-center">
          <h2 class="text-2xl font-bold text-green-700 tracking-wide uppercase">My reservation</h2>
          <p class="mt-1 text-4xl font-extrabold text-gray-900 sm:text-5xl sm:tracking-tight lg:text-6xl">Take control
            of your reservation.</p>
        </div>
      </div>
      <h2 class="text-center text-2xl font-bold">{{user?.name}}</h2>
      <h2 class="text-center text-xl">{{user?.email}}</h2>
    </div>
  </header>

  <main>
    <div class="">
      <div class="max-w-7xl mx-auto pb-12 px-4 sm:pb-16 sm:px-6 lg:px-8">
        <div class="mx-auto divide-y-2 divide-gray-200">
          <dl class="mt-6 space-y-6 divide-y divide-gray-200">
            <Disclosure as="div" v-for="(order, index) in sortedOrders" :key="index" class="border-0" v-slot="{ open }">
              <dt class="text-lg">
                <DisclosureButton class="text-left w-full flex justify-between items-center px-3 py-2 rounded bg-green-700 text-white">

                  <div class="text-sm text-white">
                    <p class="text-xl font-bold text-bord truncate">
                      Order Reference No. {{ order?.id }}<br>
                    </p>
                  </div>
                  <div class="justify-end flex">
                    <span class="ml-6 h-7 flex items-center">
                      <ChevronDownIcon :class="[open ? '-rotate-180' : 'rotate-0', 'h-6 w-6 transform']"
                        aria-hidden="true" />
                    </span>
                  </div>

                </DisclosureButton>
              </dt>
              <DisclosurePanel as="dd" style="max-height: 200vh">


                <section aria-labelledby="summary-heading" class=" mt-2 border-2 p-3 rounded border-gray-300">
                  <h2 id="summary-heading" class="sr-only">Billing Summary</h2>

                  <div class="lg:grid lg:grid-cols-12 lg:gap-x-8">
                    <div class="sm:flex lg:col-span-7">

                      <div class="mt-6 sm:mt-0">
                        <h3 class="text-base font-medium text-gray-900">
                          <span class="font-bold">Name: </span>{{user?.name}}
                        </h3>
                        <p class="mt-2 text-sm font-medium text-gray-900"><span class="font-bold">Email:
                          </span>{{user?.email}}</p>
                        <p class="mt-2 text-sm font-medium text-gray-900"><span class="font-bold">Date:
                          </span>{{order?.startdate}} <b>/</b> {{order?.finishdate}}</p>
                        <p class="mt-3 text-sm text-gray-900"> <span class="font-bold">Description: </span></p>
                      </div>
                    </div>
                  </div>
                  <div>
                    <p class="mt-3 text-sm text-gray-900"> <span class="font-bold">Product Details: </span></p>
                    <ul class="flex pt-2 flex-wrap">
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Start Date:</span> {{order?.startdate}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Finish Date:</span> {{order?.finishdate}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Start Time:</span> {{order?.starttime}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Finish Time:</span> {{order?.finishtime}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Fullday:</span> {{order?.fullday}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Guests:</span> {{order?.guests}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Amount:</span> {{order?.amount}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Product ID:</span> {{order?.product_id}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Transaction ID:</span> {{order?.transactionID}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Card Brand:</span> {{order?.cardBrand}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">last Four:</span> {{order?.lastFour}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Expire:</span> {{order?.expire}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Product:</span> {{order?.product}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Name:</span> {{order?.user.name}}</li>
                      <li class=" bg-gray-200 py-1 text-sm rounded px-2 mr-3 mb-3"><span class="font-semibold">Email:</span> {{order?.user.email}}</li>
                    </ul>
                  </div>
                  <div>
                    <!-- {{order}} -->
                  </div>
                  <div class=" rounded-lg py-6 px-6 lg:px-0 lg:py-8 lg:grid lg:grid-cols-12 lg:gap-x-8">
                    <dl class="grid grid-cols-1 gap-6 text-sm sm:grid-cols-2 md:gap-x-8  lg:col-span-5">
                      <div>
                        <dt class="font-bold text-gray-900 border-b-2 border-gray-300">Billing address :</dt>
                        <dd class="mt-3 text-gray-900">
                          <ul>
                            <li class="mb-4"><span class="font-bold">name -
                              </span><br /><span>{{order?.user.name}}</span></li>
                            <li class="mb-4"><span class="font-bold">email -
                              </span><br /><span>{{order?.user.email}}</span></li>
                            <li class="mb-4"><span class="font-bold">Address - </span><br /><span>7363 Cynthia Pass,
                                Toronto, ON N3Y 4H8</span></li>
                          </ul>


                        </dd>
                      </div>
                      <div>
                        <dt class="font-bold text-gray-900 border-b-2 border-gray-300">Payment information :</dt>
                        <dd class="mt-3 flex">
                          <div>
                            <svg aria-hidden="true" width="36" height="24" viewBox="0 0 36 24"
                              xmlns="http://www.w3.org/2000/svg" class="h-6 w-auto">
                              <rect width="36" height="24" rx="4" fill="#224DBA" />
                              <path
                                d="M10.925 15.673H8.874l-1.538-6c-.073-.276-.228-.52-.456-.635A6.575 6.575 0 005 8.403v-.231h3.304c.456 0 .798.347.855.75l.798 4.328 2.05-5.078h1.994l-3.076 7.5zm4.216 0h-1.937L14.8 8.172h1.937l-1.595 7.5zm4.101-5.422c.057-.404.399-.635.798-.635a3.54 3.54 0 011.88.346l.342-1.615A4.808 4.808 0 0020.496 8c-1.88 0-3.248 1.039-3.248 2.481 0 1.097.969 1.673 1.653 2.02.74.346 1.025.577.968.923 0 .519-.57.75-1.139.75a4.795 4.795 0 01-1.994-.462l-.342 1.616a5.48 5.48 0 002.108.404c2.108.057 3.418-.981 3.418-2.539 0-1.962-2.678-2.077-2.678-2.942zm9.457 5.422L27.16 8.172h-1.652a.858.858 0 00-.798.577l-2.848 6.924h1.994l.398-1.096h2.45l.228 1.096h1.766zm-2.905-5.482l.57 2.827h-1.596l1.026-2.827z"
                                fill="#fff" />
                            </svg>
                            <p class="sr-only">Visa</p>
                          </div>
                          <div class="ml-4">
                            <p class="text-gray-900">Ending with {{ order.lastFour}}</p>
                            <p class="text-gray-600">Expires {{ order.expire }}</p>
                          </div>
                        </dd>
                      </div>
                    </dl>

                    <dl class="mt-8 bg-gray-900 shadow rounded-xl px-7 py-5 divide-y divide-gray-500 text-sm lg:mt-0 lg:pr-8 lg:col-span-7">
                      <div class="pb-4 flex items-center justify-between">
                        <dt class="text-gray-100 font-semibold">Subtotal</dt>
                        <dd class="font-medium text-gray-200">$72</dd>
                      </div>
                      <div class="py-4 flex items-center justify-between">
                        <dt class="text-gray-100 font-semibold">Shipping</dt>
                        <dd class="font-medium text-gray-200">$5</dd>
                      </div>
                      <div class="py-4 flex items-center justify-between">
                        <dt class="text-gray-100 font-semibold">Tax</dt>
                        <dd class="font-medium text-gray-200">$6.16</dd>
                      </div>
                      <div class="pt-4 flex items-center justify-between">
                        <dt class="text-gray-100 font-bold">Order total</dt>
                        <dd class="font-bold text-indigo-500">{{(order.amount /100).toFixed(2)}} €</dd>
                      </div>
                    </dl>
                  </div>
                </section>


              </DisclosurePanel>
            </Disclosure>
          </dl>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import { QuestionMarkCircleIcon, XIcon, ChevronDownIcon } from '@heroicons/vue/outline'
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'

import moment from 'moment'


export default {
  data() {
    return {
      user: null,
      showModal: false,
      orders: [],
    }
  },

  mounted() {
    let objData = JSON.parse(localStorage.getItem('bigStore.user'));
    this.user = objData;
    console.log("this is for text", objData);
    this.axios.defaults.headers.common['Content-Type'] = 'application/json';
    this.axios.defaults.headers.common['Authorization'] = 'Bearer ' + localStorage.getItem('bigStore.jwt');
    let Orders = this.axios.get(process.env.VUE_APP_URL_API + `api/users/${this.user.id}/orders`,)
      .then(response => this.orders = response.data
      );
    console.log("to check the oeders", Orders.user_id);
  },

  /*eslint-disable */

  computed: {
    sortedOrders: function () {
      this.orders.sort((a, b) => {
        return new Date(b.id) - new Date(a.id);
      });
      return this.orders;
    },

    setUser: {
      get() {
        return this.$store.state.setUser
      }
    },
  },

  setup() {
    return {
      moment,
    }
  },

  components: {
    QuestionMarkCircleIcon,
    XIcon,
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
    ChevronDownIcon,

  },


}
</script>

<style>
.userDetail {
  display: flex;
  align-items: center;
  justify-content: center;
}

.userDetail ul li {
  padding-bottom: 10px;
}
</style>
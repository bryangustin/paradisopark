<template>
  <div class="bg-top sm:bg-top min-h-screen bg-white flex flex-col justify-center py-12 sm:px-6 lg:px-8" style="background-image: url('img/pexels-burak-kebapci-1253049.jpeg'); ; background-size: cover;">
    <div class="sm:mx-auto sm:w-full sm:max-w-m">
      <div class="mx-auto w-full max-w-sm lg:w-96 bg-white p-5 rounded-lg">
        <div>
          <h2 class="mt-6 text-3xl font-extrabold text-bord">{{$t("login.title")}}</h2>
        </div>

        <div class="mt-8">
          <div class="mt-6">
            <form @submit.prevent="handleSubmit" class="space-y-6">

              <div>
                <label for="email" class="block text-sm font-medium text-bord">
                  {{$t("login.email")}}
                </label>
                <div class="mt-1">
                  <input id="email" name="email" type="email" v-model="email" autocomplete="email" required="" class="appearance-none block w-full px-3 py-2 border border-bord rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-gold focus:border-gold sm:text-sm" />
                </div>
              </div>

              <div class="space-y-1">
                <label for="password" class="block text-sm font-medium text-bord">
                  {{$t("login.pass")}}
                </label>
                <div class="mt-1">
                  <input id="password" name="password" type="password" v-model="password" autocomplete="current-password" required="" class="appearance-none block w-full px-3 py-2 border border-bord rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-gold focus:border-gold sm:text-sm" />
                </div>
              </div>

              <div>
                <button type="submit"  class="w-full flex justify-center py-2 px-4  bg-gray-800 text-white hover:bg-gray-900 rounded-md  text-sm font-semibold">
                  {{$t("login.title")}}
                </button>
              </div>

              <div class="flex items-center justify-between">
                <div class="text-sm">
                  <router-link to="/Register" class="font-medium text-green-700 hover:text-green-900 underline font-semibold">
                    {{$t("login.crete_btn")}}
                  </router-link>
                </div>
                <div class="text-sm">
                  <router-link to="/forgetpassword" class="font-medium text-green-700 hover:text-green-900 underline font-semibold">
                    {{$t("login.forgot_pass")}}
                  </router-link>
                </div>
              </div>

           </form>
          </div>
          <div v-if="errorLogin  != 0" class="rounded-md bg-red-50 p-4 mt-10">
            <div class="flex">
              <div class="flex-shrink-0">
                <XCircleIcon class="h-5 w-5 text-red-400" aria-hidden="true" />
              </div>
              <div class="ml-3">
                <h3 class="text-sm font-medium text-red-800">
                  {{ errorLogin  }}
                </h3>
                <div class="mt-2 text-sm text-red-700">
                  {{ errorLogin  }}
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import { XCircleIcon } from '@heroicons/vue/solid'


export default {

  components: {
    XCircleIcon,
  },

  data() {
    return {
      email: "",
      password: "",
      errorLogin :"",
    }
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault()
      if (this.password.length > 0) {
        let email = this.email
        let password = this.password

        this.axios.post(process.env.VUE_APP_URL_API + 'api/login', {email, password}).then(response => {
          let user = response.data.user
          let is_admin = user.is_admin

          localStorage.setItem('bigStore.user', JSON.stringify(user))
          localStorage.setItem('bigStore.jwt', response.data.token)


          if (localStorage.getItem('bigStore.jwt') != null) {
            this.$store.commit('setUser', user)
            this.$emit('loggedIn')
            if (this.$route.params.nextUrl != null) {
              this.$router.push(this.$route.params.nextUrl)
            } else {
              this.$router.push((is_admin == 1 ? 'Dashboard' : '/'))
            }
          }
        }).catch((error)=>{
          this.errorLogin = error.response.data.error
        });
      }
    }
  },
  computed:{
    setRoute:{
      get(){
        return this.$store.state.setRoute
      }
    },
  }
}
</script>

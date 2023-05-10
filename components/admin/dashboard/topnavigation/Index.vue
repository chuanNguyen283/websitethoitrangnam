<template>
  <header class="bg-body h-20 items-center relative w-full z-10">
    <div class="flex flex-col h-full justify-center mx-auto px-3 relative">
      <div
        class="
          flex
          items-center
          pl-1
          relative
          w-full
          sm:ml-0 sm:pr-2
          lg:max-w-68
        "
      >
        <div class="flex left-0 relative w-3/4">
          <div class="flex group h-full items-center relative w-12">
            <button
              type="button"
              aria-expanded="false"
              aria-label="Toggle sidenav"
              class="text-4xl text-white focus:outline-none lg:hidden"
              @click="toggle"
            >
              &#8801;
            </button>
          </div>
        </div>
        <div
          class="
            flex
            items-center
            justify-end
            ml-5
            p-1
            relative
            w-full
            sm:mr-0 sm:right-auto
          "
        >
          <a href="#" class="block relative">

            <a-dropdown :trigger="['click']">
              <img
                v-if="!avatar"
                alt="Enoch Ndika"
                src="@/static/default.png"
                class="h-10 mx-auto object-cover rounded-full w-10"
                @click="e => e.preventDefault()"
              >
              <img
                v-else
                alt="Enoch Ndika"
                :src="avatar"
                class="h-10 mx-auto object-cover rounded-full w-10"
                @click="e => e.preventDefault()"
              >
              <a-menu slot="overlay">
                <a-menu-item key="0">
                  <a href="#" class="text-black font-medium"><i class="fa-solid fa-user pl-1 pr-2" />{{ username }}</a>
                </a-menu-item>
                <a-menu-item key="1">
                  <a href="/" class="text-black font-medium"><i class="fa-solid fa-house-user  pl-1 pr-2" />Trang Chủ</a>
                </a-menu-item>
                <a-menu-divider />
                <a-menu-item key="3" @click="logOut">
                  Đăng Xuất
                </a-menu-item>
              </a-menu>
            </a-dropdown>
          </a>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'TopNavigation',
  inject: ['toggle'],
  computed: {
    avatar () {
      return this.$store.getters.avatar
    },
    username () {
      return this.$store.getters.getUserName
    }
  },
  watch: {
    avatar () {
      console.log(this.avatar)
    }
  },
  mounted () {
    const info = JSON.parse(localStorage.getItem('info'))
    if (info && info.admin) {
      this.$store.commit('avatar', info.avatar)
      this.$store.commit('setUserName', info.username)
    }
  },
  methods: {
    logOut () {
      localStorage.removeItem('token')
      localStorage.removeItem('info')
      this.$store.commit('isUserLoggedIn', false)
      this.$store.commit('isUserSignedUp', false)
      this.$router.push('/')
    }
  }
}
</script>

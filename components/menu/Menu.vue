<template>
  <a-menu
    class="sm:font-bold lg:w-9/12  lg:text-[0.9rem] lg:bg-base lg:px-24 lg:space-x-16 hidden sm:block lg:text-black  sm:px-12 sm:bg-base"
    mode="horizontal"
    :default-selected-keys="['1']"
    :style="{ lineHeight: '80px' }"
  >
    <a-menu-item key="1">
      <nuxt-link to="/" tag="li">
        TRANG CHỦ
      </nuxt-link>
    </a-menu-item>
    <a-menu-item key="2" >
        <nuxt-link to="/cart" tag="li">
          GIỎ HÀNG
        </nuxt-link>
      </a-menu-item>
      <a-menu-item key="3" class="relative sub_shop">
      SẢN PHẨM<a-icon type="down" class="absolute leading-[78px] font-medium pl-[1px]" />
      <ul class="hidden absolute bg-[#fef5ef] item-menu_shop">
       <li @click="searchSubject(0)">
          Thời Trang
        </li>
        <li @click="searchSubject(1)">
          Phụ Kiện
        </li>
        </div>
      </ul>
    </a-menu-item>
    </a-menu-item>
    <a-menu-item key="4">
      <nuxt-link to="/about" tag="li">
        VỀ CHÚNG TÔI
      </nuxt-link>
    </a-menu-item>
  </a-menu>
</template>
<script>
export default {
  methods: {
    searchSubject (value) {
      this.$router.replace({ path: '/search', query: { keyword: '', subject: value } })
    }
  }
}
</script>

<style lang="scss" scoped>
.ant-menu-horizontal{
    border-bottom:none ;
}
.ant-menu-horizontal > .ant-menu-item:hover,
.ant-menu-horizontal > .ant-menu-item-selected{
    color: #f79837;

}
.ant-menu-horizontal > .ant-menu-item:hover,
.ant-menu-horizontal > .ant-menu-item-selected,
.ant-menu-horizontal > .ant-menu-item, .ant-menu-horizontal > .ant-menu-submenu {
    border-bottom: none;
}

.sub_shop:hover{
    .item-menu_shop{
      @apply  animate-[flipInMenu_.5s_ease-in] block;
    }
}
.item-menu_shop{
  @apply leading-none mt-[-1px] w-44 bg-[#ffffff] ;
  li{
    @apply w-full px-8 py-4 text-black hover:text-yellow_hover transition-all ease-out duration-300;

  }
}
</style>

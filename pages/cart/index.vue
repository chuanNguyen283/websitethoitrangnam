<template>
  <div class="flex flex-col">
    <header class="banner_single mb-10">
    </header>
    <div>
      <div v-if="carts.length<1" class="text-black font-medium text-2xl px-14 h-[50vh]">
        <p>
          Không có sản phẩm nào trong giỏ hàng.
        </p>
        <hr class="bg-[#cdcdcd] text-[#cdcdcd] h-[1.5px] mt-10 mb-20">
      </div>
      <table-oder v-else class=" lg:my-10 sm:my-5 px-14" />
    </div>
  </div>
</template>

<script>
import TableOder from '@/components/cart/TableOder.vue'
export default {
  components: {
    TableOder
  },
  middleware: ['user'],
  computed: {
    carts () {
      return this.$store.getters.carts
    }
  }

}
</script>

<style lang="scss">
  .banner_single{
    background-image: url('@/static/banner/banner_single.png');
    position: relative;
    background-repeat: no-repeat;
    background-size: cover cover;
    padding: 100px 0 140px 0;
    width: 100%;
  }
  </style>

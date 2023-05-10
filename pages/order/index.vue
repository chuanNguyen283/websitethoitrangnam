<template>
  <div class="flex flex-col">
    <header class="banner_single mb-10">
    </header>
    <tab-order />
  </div>
</template>

<script>
import TabOrder from '@/components/order/TabOrder.vue'

export default {
  components: {
    TabOrder
  },
  middleware: ['user']
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

<template>
  <div class="flex flex-col">
    <header class="banner_single mb-10">
    </header>
    <div class="mb-10 px-14 flex  flex-col">
      <TabAccount class="my-12" />
    </div>
  </div>
</template>

<script>
import TabAccount from '@/components/account/TabAccount.vue'
export default {
  components: {
    TabAccount
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

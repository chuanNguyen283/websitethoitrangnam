<template>
  <div class="flex flex-col">
    <header class="banner_single mb-10">>
    </header>
    <div class="my-20 grid sm:grid-cols-2 grid-cols-1 sm:px-14 px-8 gap-6">
      <div>
        <img src="@/static/imgAbout.jpg" alt="photo">
      </div>
      <div class="space-y-2">
        <h2 class="text-3xl text-black font-medium">
          ABOUT OUR  STORE
        </h2>
        <p class="text-2xl text-black font-normal">
          chuan 1
        </p>
        <p class="text-lg  font-normal">
       chuan 2
        </p>
        <p class="text-lg  font-normal">
       chuan 3
        </p>
      </div>
    </div>

  </div>
</template>

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

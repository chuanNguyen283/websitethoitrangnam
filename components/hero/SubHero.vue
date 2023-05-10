
<script>
export default {
  methods: {
    searchSubject () {
      this.$router.replace({ path: '/search', query: { keyword: '' } })
    }
  }
}
</script>
<style lang="scss">
.btn_sm{
    @apply py-[10px] px-4;
}
.img-zoom-hover img{
    transition: all .5s ease-out;
}
.img-zoom-hover:hover{
    img{
        @apply transition-all duration-500 ease-in scale-110;
    // transition: all .5s ease-in;
    // scale: 1.1;

    }
}
.btn_sm:hover{
    @apply text-black bg-white border-[1px] transition-all ease-in-out duration-200;
}
.product_var_one_text{
    @apply absolute left-10 pt-4 pb-5 px-5 w-1/2 top-1/2;
    transform: translateY(-55%);
}
.product_text_mid{
        @apply absolute left-10 pt-4 pb-5 px-5 w-1/2 top-1/2;
    transform: translateY(-20%);
}
.color_one{
    @apply text-orange
}
</style>

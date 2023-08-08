<template>
  <div>
    <h1>Halaman Product</h1>
    <div v-for="data in products" :key="data.id">
        <img :src="data.image" alt="" srcset="">
        <i>{{ data.title }} Price : {{ data.price }}</i>
    </div>
  </div>
</template>

<script>
// import { useStore } from 'vuex'
// const store = useStore();
// const getProducts = computed(() => {
//     return store.getters.getProducts
// })
// const products = computed(() => {
//     return store.state.products
// })
// onMounted(() => {
//     store.dispatch('fetchProduct')
// }),
export default {
    mounted() {
        this.$store.dispatch('fetchProduct')
    },
    computed: {
        // getProducts() {
        //     return this.$store.getter.getProducts
        // },
        products() {
            return this.$store.state.products
        }
    },
    
}
</script>

<style scoped>
img{
    height: auto;
    width: 15%;
}
</style>

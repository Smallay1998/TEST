<template>
    <div>
        <div class="grid grid-cols-4 gap-5">
            <div v-for="p in products">
                <ProductCard :product="p" />
            </div>
        </div>
    </div>
</template>

<script setup>
    definePageMeta({
        layout:'products'
    })

    // fetch data
    const { data: products} = await useFetch('https://fakestoreapi.com/products')

    useHead({
    title: 'Online Catalog | Product Page',
    meta: [
      { name: 'description', content: 'Product Catalog'}
    ]
  })
</script>

<style scoped>

</style>
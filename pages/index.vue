<template>
<div>
    <!--productsection-->

    <section>
        <select class="form-select" aria-level="Default select example" v-model="name" @change="getUrl(name)">
            <optical selected>select one</optical>
            <option :value="category.strCategory" v-for="(category, index) in categoryData.categories" :key="index">{{ category.strCategory }}</option>

        </select>
        <div class="container ms-auto grid lg:grid-cols-4 gap-3 m-4">
            <div v-for="(p, index) in data.meals" :key="index">
                <nuxt-link :to=" `products/${p.idMeal}`">
                    <product-card :product="p" />
                </nuxt-link>
            </div>
        </div>
    </section>
</div>
</template>

<script setup>
let name = "";
const url = ref(`https://www.themealdb.com/api/json/v1/1/filter.php?c=Seafood`)
const {
    data: categoryData
} = await useFetch(
    "https://www.themealdb.com/api/json/v1/1/categories.php"
);
const {
    data
} = useFetch(url, {
    refetch: true
})

function getUrl(category) {
    url.value = (`(https://www.themealdb.com/api/json/v1/1/filter.php?c=${category}`)
}
</script>

<style lang="scss" scoped>

 </style>

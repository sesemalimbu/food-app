<template>
<div>
    <div class="container m-auto grid lg:grid-cols-3 gap-5 item-center py-10">
        <div class="col-span-1">
            <img :src="meal.meals[0].strMealThumb" alt="" width="400px" height="400px" class="rounded-full">
        </div>
        <!--meal.meals-->

    </div>
    <div class="col-span-2">
        <h1 class="text-2x1 font-bold">{{ meal.meals[0].strMeal }}</h1>
        <p>{{ meal.meals[0].strInstructions }}</p>
        <h1 class="text-x1 text-red-500">video Tutorial</h1>
        <!-- <a href=""></a> -->
    </div>

</div>
</template>

<script setup>
const route = useRoute();
const {
    data: meal
} = await useFetch(`https://www.themealdb.com/api/json/v1/1/lookup.php?i=${route.params.id}`)
</script>

<style  scoped>

</style>

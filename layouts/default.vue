<template>
    <div>
       <header>
        <navbar-component></navbar-component>
       </header>

        <main>
            <slot></slot>
        </main>

        <footer class="py-5 m-3"><footer-component></footer-component></footer>
    </div>
</template>

<script setup>

</script>

<style  scoped>

</style>
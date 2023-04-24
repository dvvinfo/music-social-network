<template>
  <TopNavigation/>
  <div id="AccountView" class="account max-w-4xl mx-auto pt-10">
    <router-view />
  </div>
  <FooterSection/>
</template>

<script setup>
import FooterSection from '../components/structure/FooterSection.vue';
import TopNavigation from '../components/structure/TopNavigation.vue';

</script>

<style lang="scss" scoped>
</style>

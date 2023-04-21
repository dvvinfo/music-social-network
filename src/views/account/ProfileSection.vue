<template>
  <div class="max-w-4xl mx-auto flex">
    <div class="w-1/3">
      <img
        class="w-full rounded-lg shadow-lg"
        src="https://via.placeholder.com/500"
        alt="Profile"
      />
    </div>
    <div class="w-full pl-4">
      <div class="flex">
        <div class="w-1/2">
          <h1 class="text-2xl md:text-3xl text-left text-gray-900">Иван Иванов</h1>
          <span class="text-md text-gray-700">
            <i><b>Москва, Россия</b></i>
          </span>
        </div>
        <div class="w-1/2 mt-2">
          <RouterLinkButton btn-text="Редактировать профиль" color="green" url="/account/edit-profile"/>
        </div>
      </div>
      <ProfileInfoSection/>
      <ProfileAboutSection/>
    </div>
  </div>
</template>

<script setup>
import ProfileInfoSection from '../../components/partials/profile/ProfileInfoSection.vue'
import ProfileAboutSection from '../../components/partials/profile/ProfileAboutSection.vue'
import RouterLinkButton from '../../components/UI/RouterLinkButton.vue';
</script>

<style lang="scss" scoped></style>

<template>
  <div class="w-full bg-black text-gray-100">
    <div
      class="container mx-auto max-w-4xl h-full flex flex-wrap justify-between items-start text-start text-sm p-6 pt-8"
    >
      <div class="mb-4">
        <div class="mb-4">Другие ссылки</div>
        <router-link to="/" class="block mb-2"></router-link>
      </div>
      <div class="mb-4">
        <div class="mb-4">О нас</div>
        <p class="mb-4 loading-normal">
          123 ул. Ленина д.23 <br />
          Москва
        </p>
        <p class="text-sm">+7 950 00 00 000</p>
      </div>
    </div>
    <div
      class="container mx-auto max-w-4xl h-full flex flex-wrap justify-between items-center text-start text-sm py-6"
    > &copy;2023 МСС. Все права защищены.
    <div class=" pt-4 md:p-0 text-center md:text-right text-sm">
        <div class=" no-underline">Политика конфидициальности</div>
        <div class=" no-underline mt-4">Правила и условия</div>
        <div class=" no-underline mt-4">Контакты</div>
    </div>
</div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped></style>

<script setup lang="ts">

</script>

<template>
  <div class="h-dvh w-full flex justify-center items-center bg-[#FFE6C9] overflow-hidden register-page">
    <div class="w-3/5 h-4/5 flex register-page__body bg-white p-3 rounded-lg">
      <div class="h-full flex-1 register-img">
        <NuxtImg class="h-full" src="/images/login.png"/>
      </div>
      <div class="register-form size-full flex justify-center items-center">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.register-page {
  &__body {
    box-shadow: rgba(149, 157, 165, 0.2) 0 8px 24px;

    .register-img {
      flex: 2
    }

    .register-form {
      flex: 1;
    }
  }
}
</style>
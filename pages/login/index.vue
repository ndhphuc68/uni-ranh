<script setup lang="ts">
import {object, string} from "yup";

const schema = object({
  email: string().email('Invalid email').required('Required'),
  password: string()
      .min(8, 'Must be at least 8 characters')
      .required('Required')
})

const loginForm = reactive({
  email: undefined,
  password: undefined
})

const handleLogin = () => {

}
</script>

<template>
  <NuxtLayout :name="'register'">
    <UForm :schema="schema" :state="loginForm" class="space-y-4 w-2/3" @submit="handleLogin">
      <h2 class="font-bold">Login to your Account</h2>
      <UFormGroup label="Email" name="email">
        <UInput v-model="loginForm.email"/>
      </UFormGroup>

      <UFormGroup label="Password" name="password">
        <UInput v-model="loginForm.password" type="password"/>
      </UFormGroup>

      <UButton class="w-full flex justify-center" type="submit">
        Submit
      </UButton>
    </UForm>
  </NuxtLayout>
</template>

<style scoped lang="scss">

</style>
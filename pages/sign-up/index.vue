<script setup lang="ts">
import { object, string, ref } from 'yup'

const schema = object({
  email: string().email('Invalid email').required('Required'),
  password: string()
    .min(8, 'Must be at least 8 characters')
    .required('Required'),
  confirmPassword: string()
    .min(8, 'Must be at least 8 characters')
    .required('Required')
    .oneOf([ref('password'), 'Confirmation password does not match'])
    .required('Password confirmation is required'),
})

const signUpForm = reactive({
  email: undefined,
  password: undefined,
  confirmPassword: undefined,
})

const handleSignUp = () => {}
</script>

<template>
  <NuxtLayout :name="'register'">
    <UForm
      :schema="schema"
      :state="signUpForm"
      class="space-y-4 w-2/3"
      @submit="handleSignUp"
    >
      <h2 class="font-bold">Sign up to your Account</h2>
      <UFormGroup label="Email" name="email">
        <UInput v-model="signUpForm.email" />
      </UFormGroup>

      <UFormGroup label="Password" name="password">
        <UInput v-model="signUpForm.password" type="password" />
      </UFormGroup>

      <UFormGroup label="Confirm Password" name="confirmPassword">
        <UInput v-model="signUpForm.confirmPassword" type="confirmPassword" />
      </UFormGroup>

      <UButton class="w-full flex justify-center" type="submit">
        Submit
      </UButton>
    </UForm>
  </NuxtLayout>
</template>

<style scoped></style>

<script setup>
import BaseButton from '@/components/base-button.vue';
</script>

<template>
    <div>
        <BaseButton :theme="'primary'">Primary</BaseButton>
        <BaseButton :theme="'primary'" :soft="true">Primary</BaseButton>
        <BaseButton :theme="'primary'" :outline="true">Primary</BaseButton>
        <BaseButton :theme="'primary'" disabled>Primary</BaseButton>
        <BaseButton :theme="'primary'" :active="true">Primary</BaseButton>
    </div>

    <div class="mt-3">
        <BaseButton :theme="'secondary'">Secondary</BaseButton>
        <BaseButton :theme="'secondary'" :outline="true">Secondary</BaseButton>
        <BaseButton :theme="'secondary'" disabled>Secondary</BaseButton>
        <BaseButton :theme="'secondary'" :active="true">Secondary</BaseButton>
    </div>

    <div class="mt-3">
        <BaseButton :theme="'info'">Info</BaseButton>
        <BaseButton :theme="'info'" :outline="true">Info</BaseButton>
        <BaseButton :theme="'info'" disabled>Info</BaseButton>
        <BaseButton :theme="'info'" :active="true">Info</BaseButton>
    </div>

    <div class="mt-3">
        <BaseButton :theme="'warning'">Warning</BaseButton>
        <BaseButton :theme="'warning'" :outline="true">Warning</BaseButton>
        <BaseButton :theme="'warning'" disabled>Warning</BaseButton>
        <BaseButton :theme="'warning'" :active="true">Warning</BaseButton>
    </div>

    <div class="mt-3">
        <BaseButton :theme="'dark'">Dark</BaseButton>
        <BaseButton :theme="'dark'" :outline="true">Dark</BaseButton>
        <BaseButton :theme="'dark'" disabled>Dark</BaseButton>
        <BaseButton :theme="'dark'" :active="true">Dark</BaseButton>
    </div>
</template>

<script setup>
import BaseButton from '../components/base-button.vue';
const modalGreeting = ref(null);

function showModalGreeting() {
    modalGreeting.value.show();
}
</script>

<template>
    <div class="about">
        <h1>This is an about page</h1>
    </div>

    <BaseButton class="btn btn-info" @click="showModalGreeting">
        Greetings!
    </BaseButton>

    <ModalGreetings ref="modalGreeting"></ModalGreetings>
</template>

<style></style>

<script setup>
const modalGreeting = ref(null);

function showModalGreeting() {
    modalGreeting.value.show();
}
</script>

<template>
    <div class="about">
        <h1>This is an about page</h1>
    </div>

    <button type="button" class="btn btn-warning" @click="showModalGreeting">
        Greetings!
    </button>

    <ModalGreetings ref="modalGreeting"></ModalGreetings>
</template>

<style></style>

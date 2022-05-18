<script setup>
const _modal = ref(null);

function showEventHandler() {
    console.log('Test handler');
}

defineExpose({
    show() {
        _modal.value.showModal();
    },
});
</script>

<template>
    <BaseModal id="modalGreetings" ref="_modal" @show="showEventHandler">
        <template v-slot:modal-header>
            <BaseModalHeader>
                <BaseModalHeaderTitle>Greetings</BaseModalHeaderTitle>
                <BaseModalHeaderCloseButton
            /></BaseModalHeader>
        </template>

        <template v-slot:default>
            <BaseModalBody>
                <h3>Greetings from modal!</h3>
            </BaseModalBody>
        </template>

        <template v-slot:modal-footer>
            <BaseModalFooter>
                <BaseButton
                    type="button"
                    class="btn-secondary"
                    data-bs-dismiss="modal"
                >
                    Close
                </BaseButton>
            </BaseModalFooter>
        </template>
    </BaseModal>
</template>

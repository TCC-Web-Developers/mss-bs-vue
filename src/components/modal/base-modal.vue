<script setup>
import { ref, onMounted } from 'vue';
import { Modal } from 'bootstrap';

const emit = defineEmits(['show', 'shown', 'hide', 'hidden', 'hidePrevented']);

const modalEl = ref(null);
const _modal = ref(null);

function showModal() {
    _modal.value.show();
}

function hideModal() {
    _modal.value.hide();
}

function updateModal() {
    _modal.value.handleUpdate();
}

onMounted(() => {
    _modal.value = new Modal(modalEl.value, {});

    // console.log(modalEl.value);
    // console.log(triggerBtn.value);

    modalEl.value.addEventListener('show.bs.modal', () => {
        emit('show');
    });

    modalEl.value.addEventListener('shown.bs.modal', () => {
        emit('shown');
    });
});

defineExpose({
    showModal,
    hideModal,
    updateModal,
});
</script>

<template>
    <!-- Modal -->
    <Teleport to="body">
        <div
            v-bind="$attrs"
            :aria-labelledby="$attrs.id"
            class="modal fade"
            tabindex="-1"
            aria-hidden="true"
            ref="modalEl"
        >
            <div class="modal-dialog">
                <div class="modal-content">
                    <slot name="modal-header"> </slot>
                    <slot> </slot>
                    <slot name="modal-footer"> </slot>
                </div>
            </div>
        </div>
    </Teleport>
</template>

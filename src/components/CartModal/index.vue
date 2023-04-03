<script lang="ts">
import { Dialog, DialogPanel, TransitionRoot } from '@headlessui/vue';

export default {
    props: {
        show: {
            type: Boolean,
            required: true
        },
        close: {
            type: Function,
            required: true
        }
    },
    components: {
        TransitionRoot,
        Dialog,
        DialogPanel
    }
};
</script>

<template>
    <Dialog :open="show" @close="close()">
        <DialogPanel class="fixed bg-white p-4 top-0 inset-y-0 w-96">
            CORNO VIADO
        </DialogPanel>
    </Dialog>
</template>
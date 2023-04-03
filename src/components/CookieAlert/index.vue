<script lang="ts">
import { Dialog, DialogPanel } from '@headlessui/vue';
import jsCookie from 'js-cookie';

export default {
    data() {
        return {
            show: false
        };
    },
    mounted() {
        this.showAlert();
    },
    methods: {
        showAlert() {
            const cookie = jsCookie.get('cookie_agreed');
            if (!cookie) {
                setTimeout(() => {
                    this.show = true;
                }, 5000);
            }
        },
        agree() {
            jsCookie.set('cookie_agreed', '1');
            this.show = false;
        },
        deny() {
            jsCookie.set('cookie_agreed', '0');
            this.show = false;
        }
    },
    components: {
        Dialog,
        DialogPanel
    }
};
</script>

<template>
    <Dialog :open="show">
        <div class="fixed inset-0 bg-gray-400/50" />
        <DialogPanel
            class="fixed right-0 left-0 bottom-0 flex flex-col gap-4 lg:flex-row lg:items-center lg:justify-center bg-white rounded-lg mx-3 mb-12 lg:mb-3 p-3"
        >
            <div>Nosso site utiliza cookies para melhorar a experiência do usuário.</div>
            <div class="flex justify-between gap-3">
                <button 
                    type="button" 
                    class="bg-white border-2 border-orange-400 py-2 px-4 text-orange-400 rounded-full hover:bg-orange-400/10" 
                    @click="deny"
                >
                    Recusar
                </button>
                <button 
                    type="button"
                    class="bg-orange-400 py-2 px-4 text-white rounded-full hover:shadow-lg hover:shadow-orange-400/50 transition-all" 
                    @click="agree"
                >
                    Aceitar todos
                </button>
            </div>
        </DialogPanel>
    </Dialog>
</template>
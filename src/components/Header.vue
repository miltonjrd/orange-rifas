<script lang="ts">
import { PhShoppingCart } from '@phosphor-icons/vue';
import CartModal from '@/components/CartModal';

export default {
    data() {
        return {
            cartModalShow: false
        };
    },
    methods: {
        showCartModal() {
            this.cartModalShow = true
        }
    },
    components: {
        PhShoppingCart
    }
};
</script>

<template>
    <header class="sticky top-0 bg-white h-16 border-b">
        <div class="frame flex items-center justify-between h-full">
            <h5 class="text-orange-500">
                <NuxtLink to="/">OrangeRifas</NuxtLink>
            </h5>
            <nav class="h-full">
                <ul class="flex items-center h-full gap-6">
                    <li>
                        <button 
                            type="button" 
                            class="group opacity-70 hover:opacity-100 hover:bg-orange-50 p-2 rounded-full transition-colors"
                            @click="showCartModal"
                        >
                            <ph-shopping-cart :size="20" class="group-hover:text-orange-500" color="currentColor" />
                        </button>
                    </li>
                </ul>
            </nav>
            <CartModal :show="cartModalShow" :close="() => { cartModalShow = false }" />
        </div>
    </header>
</template>
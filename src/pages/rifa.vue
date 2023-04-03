<script lang="ts">
import { PhPlus, PhMinus } from '@phosphor-icons/vue';

export default {
    data() {
        return {
            amount: 1
        };
    },
    methods: {
        increaseAmount() {
            this.amount += 1;
        },
        decreaseAmount() {
            if (!(this.amount - 1 <= 0))
                this.amount -= 1;
        },
        setAmount(amount: number) {
            this.amount = amount;
        }
    },
    components: {
        PhPlus,
        PhMinus
    }
};
</script>

<template>
    <div class="bg-white max-w-2xl mx-auto p-3 pb-8 mt-10 shadow-lg shadow-gray-400/10">
        <div>
            <div class="bg-gray-200 h-72 w-full mb-3 rounded-lg" />
            <h3 class="mb-0">Titulo dessa rifa</h3>
            <p class="mb-4">Descrição dessa rifa</p>
            <div class="flex justify-center my-4">
                <span class="block text-2xl text-green-500">{{ amount }} x R$ 20,00</span>
            </div>
            <div class="flex justify-between">
                <h5 class="font-normal">Promoções:</h5>
                <button type="button"></button>
            </div>
            <div class="flex flex-wrap gap-1 mb-3">
                <button class="bg-orange-300 hover:bg-orange-400 text-white rounded px-1">15x por R$ 15,00</button>
            </div>
            <h5 class="font-normal">Quantidade:</h5>
            <div class="grid grid-cols-2 md:grid-cols-4 gap-3">
                <button 
                    type="button" 
                    class=" bg-orange-300 hover:bg-orange-300/80 h-12 text-white rounded-xl transition-all"
                    @click="setAmount(5)"
                >
                    5
                </button>
                <button 
                    type="button" 
                    class="highlight-btn bg-white after:bg-orange-400 after:text-white hover:bg-orange-50 border-2 border-orange-400 h-12 text-orange-400 rounded-xl transition-all"
                    @click="setAmount(10)"
                >
                    10
                </button>
                <button 
                    type="button" 
                    class="bg-orange-300 hover:bg-orange-300/80 h-12 text-white rounded-xl transition-all"
                    @click="setAmount(50)"
                >
                    50
                </button>
                <button 
                    type="button" 
                    class="bg-orange-300 hover:bg-orange-300/80 h-12 text-white rounded-xl transition-all"
                    @click="setAmount(100)"
                >
                    100
                </button>
            </div>
            <div class="flex my-6 sm:w-96 mx-auto">
                <button type="button" class="flex justify-center items-center bg-orange-300 hover:bg-orange-300/80 h-12 w-10 text-white rounded-l" @click="decreaseAmount">
                    <ph-minus :size="20" color="#ffffff" />
                </button>
                <div class="flex flex-grow items-center justify-center text-orange-500 border border-orange-300">
                    {{ amount }}
                </div>
                <button type="button" class="flex justify-center items-center bg-orange-300 hover:bg-orange-300/80 h-12 w-10 text-white rounded-r" @click="increaseAmount">
                    <ph-plus :size="20" color="#ffffff" />
                </button>
            </div>
            <div class="flex justify-end">
                <button 
                    type="button" 
                    class="bg-orange-300 text-white w-full sm:w-auto px-6 py-3 rounded-full hover:shadow-lg hover:shadow-orange-300/50 transition-shadow"
                >
                    Finalizar compra
                </button>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .highlight-btn {
        position: relative;

        &::after {
            content: 'mais popular';
            position: absolute;
            right: 0;
            top: 0;
            transform: translateY(-50%);
            padding: 0 .5rem;
            border-radius: .5rem;
            font-size: 14px;
        }
    }
</style>
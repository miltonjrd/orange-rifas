<script lang="ts">
export default {
    data() {
        return {
            raffles: new Array(5).fill(0)
        };
    }
};
</script>

<template>
    <div class="frame py-4">
        <h4>PRÊMIOS</h4>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 2xl:grid-cols-4 gap-4">
            <RaffleCard 
                v-for="raffle in raffles" 
                title="Rifaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa" 
                description="Descrição dessa rifa Descrição dessa rifa Descrição dessa rifa Descrição dessa rifa Descrição dessa rifa Descrição dessa rifa Descrição dessa rifa " 
                :price="32" 
            />
        </div>
    </div>
</template>
<script lang="ts">
export default {
    props: {
        title: {
            type: String,
            required: true
        },
        description: {
            type: String,
            required: true
        },
        price: {
            type: Number,
            required: true
        }
    }
};
</script>

<template>
    <div class="bg-white h-40 p-3 rounded-md shadow-md shadow-gray-400/5">
        <NuxtLink to="rifa">
            <h5 class="w-full overflow-hidden text-ellipsis">{{ title }}</h5>
        </NuxtLink>
        <p class="line-clamp-2 text-gray-600">{{ description }}</p>
        <strong class="text-green-500 text-2xl">{{ price.toLocaleString('pt-br', { style: 'currency', currency: 'BRL' }) }}</strong>
    </div>
</template>

<style scoped>
p {
    margin-bottom: 1rem;
}
</style>
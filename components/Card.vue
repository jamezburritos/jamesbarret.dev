<script setup lang="ts">
defineProps<{
    title: string
    tags?: string[]
}>()
</script>

<template>
    <section class="card">
        <h3>{{ title }}</h3>
        <p><slot /></p>
        <div class="tags">
            <p class="tag" v-for="tag in tags">{{ tag }}</p>
        </div>
    </section>
</template>

<style scoped lang="scss">
.card {
    padding: 24px;
    margin-bottom: 16px;

    display: flex;
    flex-direction: column;
    gap: 16px;

    border-radius: 8px;

    background: rgba(black, 20%);

    .tags {
        width: 100%;

        display: flex;
        gap: 8px;
    }

    .tag {
        padding: 4px 12px;

        border-radius: 16px;
        background: #3d4a78;
    }
}
</style>

<script setup lang="ts">
defineProps<{
    tags?: string[]
    link?: string
}>()
</script>

<template>
    <section class="card">
        <div id="top">
            <h3><slot name="heading" /></h3>
            <h4><slot name="subheading" /></h4>
        </div>

        <p><slot /></p>

        <div id="bottom">
            <div id="tags">
                <p class="tag" v-for="tag in tags">{{ tag }}</p>
            </div>
            <div id="spacer" />
            <a id="link" target="_blank" :href="link"><slot name="link" /></a>
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

    background: rgba(#121933, 50%);
    backdrop-filter: blur(8px);

    h4 {
        margin-top: 0.25rem;

        font-weight: 500;
    }

    #bottom {
        display: flex;
    }

    #tags {
        display: flex;
        gap: 8px;
    }

    #spacer {
        flex: 1;
    }

    .tag,
    #link {
        padding: 4px 12px;
    }
    .tag {
        border-radius: 16px;
        background: #3d4a78;
    }
}
</style>

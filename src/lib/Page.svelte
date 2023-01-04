<script lang="ts">
    export let title: string;
</script>

<div class="page"> 
    <div class="content">
        <h1>{title}</h1>
        <slot></slot>
    </div>
</div>

<style lang="sass">
.page
    display: flex 
    justify-content: center
    
    .content 
        margin: 0 50px 0 50px
        flex: 0 1 1440px

        h1 
            margin: 30px 0 0 0
</style>

<script> 
    import '../app.sass'
</script>

<div class="navbar"> 
    <a class="text" href="/">
        <h2>James Barret</h2>
        <p>Developer / Designer / Student</p>
    </a>
    
    <nav class="links">
        <a href="/about">About Me</a>
        <img src="/images/divider.svg"/>
        <a href="/work">My Work</a>
        <img src="/images/divider.svg"/>
        <a href="/contact">Get in Touch</a>
    </nav>
</div>

<main>
    <slot></slot>
</main>

<style lang="sass">
a 
    text-decoration: none 

.navbar 
    position: fixed
    left: 0
    right: 0
    padding: 40px 50px 40px 50px 

    display: flex 
    flex-direction: row
    align-items: center

    background: #FFFEFC

    > * 
        flex: 1 0

    .text 
        flex-basis: 200px 

    .links
        flex-basis: 300px
        display: flex
        justify-content: flex-end
        gap: 20px

main 
    padding-top: 142px
</style>

<div class="page">
    <div class="content"> 
        <img src="/images/homepage/face.png"/>
        <div class="text"> 
            <h1>Hi There</h1>
            <h2>I'm James</h2>
            <p>I'm a developer, designer and student based in Johannesburg, South Africa. I have 2+ years of development experience and I aim to create simple, effective solutions to any problems presented to me.</p>
        </div>
    </div>
</div>

<style lang="sass">
.page 
    position: absolute
    top: 0
    width: 100vw
    height: 100vh
    z-index: -100

    display: flex 
    align-items: center

.content 
    margin: 0 50px 0 50px
    width: 100%

    display: flex  
    justify-content: center
    gap: 40px

    .text 
        flex: 0 1 380px 

@media screen and (max-width: 780px)
    .content 
        img 
            display: none
</style>

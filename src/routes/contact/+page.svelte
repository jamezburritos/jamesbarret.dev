<script lang="ts"> 
    import Page from "$lib/Page.svelte";

    interface Link {
        title: string,
        text: string, 
        url: string
    }

    const links: Link[] = [ 
        {
            title: "Email",
            text: "jamesbarret715@gmail.com",
            url: "mailto:jamesbarret715@gmail.com"
        },
        {
            title: "Github",
            text: "jamezburritos",
            url: "https://github.com/jamezburritos"
        },
        {
            title: "Discord",
            text: "sennheiser#9579",
            url: "https://discord.com/users/527508031509102641"
        },
        {
            title: "Instagram",
            text: "@james.barret_",
            url: "https://instagram.com/james.barret_"
        },
        {
            title: "Twitter",
            text: "@jamesbarret_",
            url: "https://twitter.com/jamesbarret_"
        },
        {
            title: "LinkedIn",
            text: "James Barret",
            url: "https://www.linkedin.com/in/james-barret-986491247/"
        }
    ]

    const pivot = Math.ceil(links.length / 2)
</script>

<Page title="Get in Touch"> 
    <div class="links">
        <div> 
            {#each links.slice(0, pivot) as link (link.title)}
            <section>
                <h3>{link.title}</h3>
                <a href={link.url}>{link.text}</a>
            </section>
            {/each}
        </div>
        <div>
            {#each links.slice(pivot) as link (link.title)}
            <section>
                <h3>{link.title}</h3>
                <a href={link.url}>{link.text}</a>
            </section>
            {/each}
        </div>
    </div>
</Page>

<style lang="sass">
.links 
    margin-top: 20px

    display: flex 
    gap: 80px

    div
        margin: 0
        padding: 0

        flex: 0 1
        display: flex 
        flex-direction: column
        gap: 20px

        list-style: none

@media screen and (max-width: 500px)
    .links 
        flex-direction: column
        gap: 20px
</style>

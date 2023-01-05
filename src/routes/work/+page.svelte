<script lang="ts"> 
    import Page from "$lib/Page.svelte";

    interface section {
        title: string, 
        image: string,
        link?: { url: string, text: string },
        description: string, 
        tags?: string[]
    }

    const sections: section[] = [
        {
            title: "This Site",
            image: "/images/work/jamesbarret.png",
            link: { url: "https://jamesbarret.dev", text: "jamesbarret.dev"},
            description: "I built this site from scratch.<br>I mocked up the design using Figma, carefully selecting colors and fonts that came together in a clean and simple user experience.<br>I implemented the design using SvelteKit, my framework of choice, and generated a static webpage to balance page performance and ease of development.",
            tags: [ "Figma", "SvelteKit", "Web Development" ]
        }
    ]

    // I created this site from scratch using <strong>Figma</strong> and <strong>SvelteKit</strong>.<br>
</script>

<Page title="My Work"> 
    <div class="content">
        {#each sections as section (section.title)} 
        <div class="section"> 
            <div class="details">
                <div class="top">
                    <h2>{section.title}</h2>
                    {#if section.link}
                    <a href={section.link.url}>{section.link.text}</a>
                    {/if}
                    <p>{@html section.description}</p>
                </div>
                {#if section.tags}
                <ul> 
                    {#each section.tags as tag}
                    <li>{tag}</li>
                    {/each}
                </ul>
                {/if}
            </div>

            <img alt={section.title} src={section.image}/>
        </div>
        {/each}
    </div>
</Page>

<style lang="sass">
.content 
    display: flex 
    flex-direction: column 
    gap: 20px

.section 
    margin-top: 20px

    display: flex 
    gap: 100px

    .details 
        flex: 1
        display: flex
        flex-direction: column

        a
            margin-bottom: 15px

        .top 
            flex-grow: 1
            display: flex
            flex-direction: column

        ul 
            padding: 0
            margin: 15px 0 0 0 

            display: flex 
            justify-self: flex-end
            gap: 15px

            list-style-type: none

            li 
                padding: 5px 10px 5px 10px 
                border: 1px solid #4D4D4D

    img 
        height: auto 
        width: 100%
        max-width: 600px
        flex: 1 

        box-shadow: 0 4px 8px -2px #BFBFBF

        object-fit: contain

@media screen and (max-width: 1250px)
    .section    
        flex-direction: column-reverse
        gap: 20px

@media screen and (max-width: 440px)
    ul 
        flex-direction: column
        
        li 
            width: fit-content
</style>

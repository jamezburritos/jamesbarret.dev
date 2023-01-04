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
            description: "At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus.",
            tags: [ "Web Development", "SvelteKit", "Design" ]
        },
{
            title: "This Site",
            image: "/images/work/jamesbarret.png",
            link: { url: "https://jamesbarret.dev", text: "jamesbarret.dev"},
            description: "At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus.",
            tags: [ "Web Development", "SvelteKit", "Design" ]
        }, 
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
    padding-bottom: 40px

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
                /* border-radius: 24px */

    img 
        height: 300px 
        width: auto
        flex: 1 

        box-shadow: 0 4px 8px -2px #BFBFBF

        object-fit: contain
</style>

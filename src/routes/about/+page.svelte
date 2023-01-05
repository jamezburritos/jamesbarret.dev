<script lang="ts"> 
    import Page from "$lib/Page.svelte";
</script>

<Page title="About Me"> 
    <div class="content">
        <div class="left">
            <h2>I'm James.</h2>
            <p>I'm a developer, designer, and student based in Johannesburg, South Africa.<br>I love listening to music, playing games, and spending time with my friends.<br>I've been programming for 7 years and designing UI for 1 year.<br>I come up with simple, effective solutions to any problems that I meet.</p>
        </div>

        <div class="right"> 
            <h2>My Skills</h2>
            <div class="skills">
                <div> 
                    <section class="front-end">
                        <h3>Front End Languages</h3>
                        <ul> 
                            <li>Typescript</li>
                            <li>HTML</li>
                            <li>SCSS</li>
                        </ul> 
                    </section>
                    <section> 
                        <h3>Front End Frameworks</h3>
                        <ul> 
                            <li>SvelteKit</li>
                        </ul>
                    </section>

                </div>

                <div class="back-end"> 
                    <section> 
                        <h3>Programming Languages</h3>
                        <ul> 
                            <li>Python</li>
                            <li>C/C++</li>
                            <li>Rust</li>
                        </ul>
                    </section>
                    <section> 
                        <h3>Other Skills</h3>
                        <ul>
                            <li>Linux Systems</li>
                            <li>Nginx</li> 
                        </ul>
                    </section>
                </div>

                <div class="creative">
                    <section> 
                        <h3>Creative Software</h3>
                        <ul> 
                            <li>Adobe Photoshop</li>
                            <li>Adobe Illustrator</li>
                            <li>Figma</li>
                        </ul>
                    </section>
                </div>
        </div>

        <h2>My Education</h2>
        <div class="education"> 
            <section> 
                <div class="left">
                    <p>2021 - Present</p>
                </div>
                <div class="right">
                    <h3>Cambridge International A-Levels</h3>
                    <p>St John's College Sixth Form</p>
                </div>
            </section> 
            <section>
                <div class="left">
                    <p>2018-2021</p>
                </div>
                <div class="right">
                    <h3>High School</h3>
                    <p>St John's College</p>
                </div>
            </section>
        </div>
    </div>
</Page>

<style lang="sass">
.content 
    display: flex 
    gap: 100px

    > div 
        flex: 1
        display: flex 
        flex-direction: column

    .right > div 
        margin-bottom: 40px

    .skills 
        display: flex 

        div 
            flex: 1
            display: flex 
            flex-direction: column
            gap: 15px

        ul
            margin: 0
            padding: 0

            list-style: none

    .education 
        display: flex
        flex-direction: column
        gap: 15px

        section
            display: flex

            .left 
                flex: 1 

            .right
                flex: 2

@media screen and (max-width: 1460px)        
    .content 
        flex-direction: column
        gap: 40px

@media screen and (max-width: 760px)
    .skills 
        flex-direction: column
        gap: 15px

        .creative 
            order: -1

@media screen and (max-width: 500px)
    .education section
        flex-direction: column-reverse
</style>

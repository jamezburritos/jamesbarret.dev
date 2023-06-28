<script setup lang="ts">
useHead({
    title: "Hi, I'm James"
})

useSeoMeta({
    title: 'James Barret',
    ogTitle: 'James Barret',
    description: "Hi, I'm James. This is my personal webpage."
})

onMounted(() => {
    document.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
    document.removeEventListener('scroll', handleScroll)
})

const handleScroll = () => {
    scrollY.value = window.scrollY
}

const scrollY = ref(0)
</script>

<template>
    <main>
        <img id="mountains" src="/assets/mountains.svg" />
        <img id="sun" src="/assets/sun.svg" />
        <figure id="sky" />
        <div id="content">
            <div id="left">
                <h1>Hi, I'm<br />James Barret<span id="dot">.</span></h1>
                <div id="links">
                    <a
                        class="link"
                        alt="github"
                        href="https://github.com/jamezburritos"
                        target="_blank"
                    >
                        <img src="/assets/github.svg" />
                    </a>
                    <a
                        class="link"
                        alt="instagram"
                        href="https://instagram.com/james.barret_"
                        target="_blank"
                    >
                        <img src="/assets/instagram.svg" />
                    </a>
                    <a
                        class="link"
                        alt="twitter"
                        href="https://twitter.com/jamesbarret_"
                        target="_blank"
                    >
                        <img src="/assets/twitter.svg" />
                    </a>
                    <a
                        class="link"
                        alt="email"
                        href="mailto:jamesbarret715@gmail.com"
                        target="_blank"
                    >
                        <img src="/assets/email.svg" />
                    </a>
                </div>
                <p>
                    I'm a student based in Johannesburg, South Africa. I'm interested in
                    engineering, design, and computer science. I'm looking to study mechanical
                    engineering, with an aim to work as an engineer. I love listening to music, and
                    playing video games with my friends.
                </p>
            </div>
            <div id="right">
                <h2 class="section-header">Projects</h2>
                <Card
                    :tags="['Web Development', 'Nuxt3', 'Vue']"
                    link="https://github.com/jamezburritos/jamesbarret.dev"
                >
                    <template #heading>jamesbarret.dev</template>
                    I built this site from scratch using Nuxt, a framework built on Vue.js. It
                    serves as a one-stop-shop for all things me, including my past projects,
                    experience, and information. The goal is for prospective schools and employers
                    to look at this site and be able to get all they need to know about me at a
                    glance.
                    <template #link>View Source</template>
                </Card>
                <h2 class="section-header">Education</h2>
                <Card link="https://stjohnscollege.co.za/sixth-form">
                    <template #heading>St John's Sixth Form</template>
                    <template #subheading>2022 - Current</template>
                    I'm reading Cambridge International A-Levels at St John's. I'm in my final year,
                    with Mathematics, Further Mathematics, Physics, and Computer Science.
                    <template #link>Website</template>
                </Card>
                <h2 class="section-header">Misc.</h2>
                <Card>
                    <template #heading>Contact</template>
                    The best way to get in touch with me is via email. Give me a shout here:
                    <br /><br />
                    Email: <a href="mailto:jamesbarret715@gmail.com">jamesbarret715@gmail.com</a>
                </Card>
                <Card>
                    <template #heading>Tech I Love</template>
                    I'm familiar with a lot of tools, but here's a list of the ones I'm most
                    comfortable with working on:
                    <br /><br />
                    My first choices for personal projects:
                    <ul>
                        <li>Vue (Nuxt)</li>
                        <li>Svelte (SvetleKit)</li>
                        <li>Typescript</li>
                        <li>Appwrite</li>
                        <li>Postgres</li>
                        <li>Vercel</li>
                        <li>C/C++</li>
                        <li>Figma</li>
                    </ul>
                    <br /><br />
                    Other tools that I've learned/used:
                    <ul>
                        <li>Python</li>
                        <li>Java (JavaFX GUIs)</li>
                        <li>Rust</li>
                        <li>C# (Unity)</li>
                        <li>Onshape</li>
                        <li>Adobe Photoshop/Illustrator</li>
                    </ul>
                </Card>
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
main {
    width: 100dvw;
    height: 100dvh;
}

#content {
    position: relative;
    z-index: 10;

    padding: 96px;

    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 64px;
}

#left {
    position: sticky;
    top: 128px;
    height: 500px;

    margin-top: calc(128px - 96px);

    display: flex;
    flex-direction: column;
    gap: 32px;

    #dot {
        color: #e9a164;
    }

    #links {
        display: flex;
        align-items: center;
        gap: 24px;

        .link {
            width: 48px;
            height: 48px;

            transition: opacity 150ms linear;
        }

        .link:hover {
            opacity: 70%;
        }
    }

    p {
        max-width: min(100%, 640px);
        font-size: 1.25rem;
    }
}

#right {
    display: flex;
    flex-direction: column;
    gap: 8px;

    ul {
        display: grid;
        grid-template-columns: repeat(2, minmax(0, 1fr));

        max-height: 4rem;
    }
}

#mountains {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    height: auto;
    z-index: 1;
}

#sun {
    position: fixed;
    bottom: 0;
    left: calc(50% + 64px);
    width: 25%;
    height: auto;
    z-index: 0;

    transform: translateY(v-bind("(scrollY * -0.25) + 'px'"));
}

#sky {
    position: fixed;
    top: 0;
    left: 0;
    width: 100dvw;
    height: 100dvh;
    z-index: -1;

    background: radial-gradient(
        131.3% 75.69% at 63.05% 88.75%,
        #ffa550 0%,
        #b05648 50%,
        #3d4a78 100%
    );
}
</style>

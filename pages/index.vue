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
                    I'm a student based in Johannesburg, South Africa. Here's a sentence about a
                    cool thing that I built and the people it helps. This is about the type of
                    person I am and what I like to do in my free time so you know I'm not a robot.
                    Here's one last interesting sentence so that you remember me a bit better.
                </p>
            </div>
            <div id="right">
                <h2 class="section-header">Projects</h2>
                <Card title="jamesbarret.dev" :tags="['Web Development', 'Nuxt3', 'Vue']">
                    Irure dolor elit sint velit et consequat. Fugiat amet labore nostrud ex id magna
                    dolore nostrud exercitation non ipsum. Officia proident ad proident velit
                    laborum nulla. Ad ullamco consectetur ullamco mollit tempor veniam quis est
                    reprehenderit commodo exercitation. Magna ullamco magna proident mollit ullamco
                    dolore voluptate pariatur exercitation consequat non ullamco ullamco nisi.
                    Reprehenderit velit nostrud duis consectetur fugiat ipsum.
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

            cursor: pointer;

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

<script>
    import { fly, fade } from 'svelte/transition'
    let src = '/assets/svg/royalblueHeader.svg'
    let project1 = '/assets/projects/jaems.png'
    let project2 = '/assets/projects/latte-site.jpg'
    let project3 = '/assets/projects/market.png'
    let previousSlide = '/assets/svg/back.svg'
    let nextSlide = '/assets/svg/next.svg'

    let index = 0
    let slide = 0

    const Projects = [project1, project2, project3]

    const next = () => {
        index = (index + 1) % Projects.length
        slide = (slide + 1) % projects.length
    }

    const previous = () => {
        if (index && slide) {
            index = (index - 1) % Projects.length
            slide = (slide - 1) % projects.length
        }
    }

    const projects = [
        { Jaemsounds: 'https://www.jaemsounds.com/' },
        { LatteLuv: 'https://latteluv.netlify.app/' },
        { MarketAvenue: 'https://marketavenue.netlify.app/' },
    ]

    const projects_url = [
        { 0: 'https://github.com/LuisOcasio/Jaemsounds-Gatsby-WP-AWS' },
        { 1: 'https://github.com/LuisOcasio/latte-luv' },
        { 2: 'https://github.com/Lambda-School-Labs/quick-street-be' },
    ]

    const projects_about = [
        {
            0: 'A Headless WordPress site created for a client in the music industry. This client wanted his music to be streamed and downloaded across various types of devices.   ',
        },
        {
            1: 'Single page application that gives its user a fast and snappy feel. This is possible because we are rendering our components and not having to retrieve data from a server.',
        },
        {
            2: "During an 8 week period I worked along 5 other developers and a UX designer to create 'Market Avenue'. An application that brings local vendors and locals closer.",
        },
    ]

    const technologies = [
        {
            id: 1,
            project: [
                '\nGatsby\nWordPress\nGraphql\nAWS-Services\namplify\nroute53    \nlightsail',
            ],
        },
        { id: 2, project: ['\nReact\nSASS'] },
        { id: 3, project: ['\nReact\nmongoDB\nnode\nexpress'] },
    ]

    $: project = Object.keys(projects[slide])
    $: url = Object.values(projects[slide])
    $: git = Object.values(projects_url[slide])
    $: about = Object.values(projects_about[slide])
</script>

<div class="carousel_wrapper">
    <div class="carousel">
        <div class="previous_wrapper">
            <img
                class="previous"
                alt="go-back-arrow"
                src={previousSlide}
                on:click={previous}
            />
        </div>

        <div class="slide">
            <section class="slide_title">
                <h5>{project}</h5>
            </section>

            {#each [Projects[index]] as src (index)}
                <img
                    class="carousel-image"
                    alt="landing page of project"
                    src={src}
                    in:fly={{ x: -50, duration: 2000 }}
                />
            {/each}
        </div>

        <div class="text-wrapper">
            <div class="text-section">
                <section class="section">
                    <h5 class="section_title">About this project</h5>
                    <p class="section_paragraph">{about}</p>
                </section>

                <section class="section">
                    <h5 class="tech_title">Tech Stack used</h5>
                    <div class="stack_list_wrapper">
                        {#each [technologies[index]] as { id, project }}
                            <p>
                                {project.map((e) => {
                                    return e.toString()
                                })}
                            </p>
                        {/each}
                    </div>
                </section>

                <div class="project_buttons">
                    <a href={git}>
                        <button class="code">Code</button>
                    </a>
                    <a href={url}>
                        <button class="view">View</button>
                    </a>
                </div>
            </div>
        </div>
        <div class="next_wrapper">
            <img
                class="next"
                alt="next-arrow"
                src={nextSlide}
                on:click={next}
            />
        </div>
    </div>
</div>

<style>
    .carousel_wrapper {
        height: 650px;
    }

    .carousel {
        display: flex;
        height: 100%;
        width: 100%;
        background-color: #15202b;
    }

    .slide {
        width: 60%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        height: 90%;
        padding: 1.5rem;
    }

    .slide_title {
        font-size: small;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        padding: 0.5rem;
    }

    .carousel-image {
        width: 80%;
        height: 85%;
    }
    .previous_wrapper {
        background-color: #21367f;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .previous {
        width: 40px;
        z-index: 1;
        padding: 0.5rem;
    }
    .next_wrapper {
        background-color: #21367f;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .next {
        width: 40px;
        z-index: 1;
        padding: 0.5rem;
    }
    .project_buttons {
        display: flex;
        justify-content: space-around;
        align-items: center;
        width: 100%;
        margin-top: 2rem;
    }
    .code {
        background-color: #21367f;
        color: #fff;
        border: 2px solid #2dfafc;
        width: 130px;
        height: 32.5px;
        text-decoration: none;
        border-radius: 35px;
        font-size: small;
    }
    .view {
        color: #fff;
        border: 2px solid #2dfafc;
        background-color: #21367f;
        width: 130px;
        height: 32.5px;
        text-decoration: none;
        border-radius: 35px;
        font-size: small;
    }
    .text-wrapper {
        display: flex;
        justify-content: flex-end;
        width: 50%;
        border-left: 2px solid #d617bd;
        padding: 1.5rem;
    }
    .text-section {
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 100%;
    }
    .section {
        height: 100%;
        display: flex;
        flex-direction: column;
        font-size: small;
        align-items: center;
        justify-content: space-between;
        width: 100%;
        text-align: center;
    }
    .section_paragraph {
        width: 100%;
        height: 67%;
    }
    .section_title {
        border-bottom: 2px solid #d617bd;
        width: 50%;
        padding: 0.5rem;
    }
    .tech_title {
        border-bottom: 2px solid #d617bd;
        width: 50%;
        padding: 0.5rem;
    }
    .stack_list {
        width: 100%;
        height: 100%;
    }
    .stack_list_wrapper {
        height: 100%;
        display: flex;
        align-items: center;
        width: 100%;
        word-spacing: 30rem;
        line-height: 2rem;
        justify-content: center;
    }
</style>

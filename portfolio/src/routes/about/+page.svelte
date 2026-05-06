<script lang="ts">
    import type { PageProps } from './$types';
    let { data }: PageProps = $props();
    import SkillTree from '$lib/components/SkillTree.svelte';
</script>


<div class='container'>
    <div class='bio'>
        <h2>Hello,</h2>
        <p style="font-size: 18px;">
            Based in Bangkok, Thailand, I am a
            <span>
                <a href="education" class="link">
                    Biomedical Engineering Graduate from Mahidol University
                </a>
            </span> who specializes in 
            <span>
                <a href="portfolio" class="link">
                    integrating complex systems to work together and manipulating various forms of abstract data into intuitive visualizations.
                </a>
            </span>
            My versatility and adaptability allows me to apply my skill to solve problems in multiple field of studies, even those which are non-medical.
            As you can tell by interacting with the site, my philosophy is to keep my work simple and robust.
        </p>

        <h3>Languages</h3>
        <ul class="list-disc list-outside pl-5 text-xl">
            <li>Thai - Native</li>
            <li>English - C1 (Advanced)</li>
        </ul>

        <h3>Soft Skills</h3>
        <ul class="list-disc list-outside pl-5 text-2xl">
            <li>Creativity</li>
            <li>Adaptability</li>
            <li>Resourcefulness</li>
        </ul>
    </div>
    <div class='skill'>
        <h3>Technical Skills</h3>
        <SkillTree />
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: row;
        margin: 50px auto;
        gap: 60px;
        padding: 2%;
        justify-content: center;
    }

    .bio {
        text-align: justify;
        width: 40vw;
    }

    .bio h2 {
        font-size: 60px;
    }

    .bio h3 {
        margin-top: 10%;
        font-size: 40px;
    }

    .link {
        color: rgb(165, 165, 165);
        transition: color 0.2s ease;
    }

    .link:hover {
        color: rgb(47, 119, 47);
    }

    .skill {
        background-color: rgb(172, 199, 172);
        border-radius: 8px;
        width: 100%;
        height: auto;
        padding: 2%;
    }

    .skill h3 {
        font-size: 50px;
        color: azure;
    }

</style>
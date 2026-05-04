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
                    manipulating various forms of abstract data into tangible objective visualization.
                </a>
            </span>
            My versatility and adaptability allows me to apply my skill to solve problems in multiple field of studies, even those which are non-medical.
        </p>

        <h3>Languages</h3>
        <ul class="list-disc list-outside pl-5 text-3xl">
            <li>Thai - Native</li>
            <li>English - C1</li>
        </ul>

        <h3>Soft Skills</h3>
        <ul class="list-disc list-outside pl-5 text-2xl">
            <li>Creativity</li>
            <li>Adaptability</li>
            <li>Resourcefulness</li>
        </ul>
    </div>
    <div class='skill'>
        <h3>Hard Skills</h3>
        <SkillTree />
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: row;
        margin: 50px auto;
        gap: 60px;
        padding: 5%;
        justify-content: center;
        background-color: rgb(236, 236, 236);
    }

    .bio {
        text-align: justify;
        width: 60vw;
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
    }

    .link:hover {
        color: rgb(81, 196, 98);
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
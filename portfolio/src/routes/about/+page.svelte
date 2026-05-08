<script lang="ts">
    import type { PageProps } from './$types';
    let { data }: PageProps = $props();
    import { fade } from 'svelte/transition';
    import SkillTree from '$lib/components/SkillTree.svelte';
</script>

<div in:fade={{duration: 300}} class='container'>
    <div class='bio'>
        <h2>Hello,</h2>
        <p class="bio-text">
            Based in Bangkok, Thailand, I am a
            Biomedical Engineering Graduate from Mahidol University who specializes in 
            integrating complex systems to work together and manipulating various forms of abstract data into intuitive visualizations.
            My versatility and adaptability allows me to apply my skill to solve problems in multiple field of studies, even those which are non-medical.
            As you can tell by interacting with the site,
        </p>
        <p class="philosophy-text">
            "my philosophy is to keep my work simple and robust."
        </p>

        <h3>Languages</h3>
        <ul class="list-disc list-inside language-list">
            <li>Thai - Native</li>
            <li>English - C1 (Advanced)</li>
        </ul>

        <h3>Soft Skills</h3>
        <ul class="list-disc list-inside soft-skills-list">
            <li>Creativity</li>
            <li>Adaptability</li>
            <li>Resourcefulness</li>
        </ul>
    </div>
    <div class='skill'>
        <h3>Technical Skills</h3>
        <div class="skill-tree-wrapper">
            <SkillTree />
        </div>
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: row;
        margin: 50px auto;
        gap: 60px;
        padding: 2% 5%;
        justify-content: center;
        max-width: 1400px;
    }

    .bio {
        text-align: justify;
        width: 45%;
    }

    .bio h2 {
        font-size: clamp(40px, 5vw, 60px);
        margin-bottom: 20px;
    }

    .bio-text {
        font-size: clamp(16px, 1.2vw, 18px);
        line-height: 1.6;
    }

    .philosophy-text {
        font-size: clamp(1.2rem, 2vw, 1.5rem);
        color: darkgreen; 
        text-align: center; 
        margin-top: 50px;
    }

    .bio h3 {
        margin-top: 40px;
        font-size: clamp(28px, 3vw, 40px);
    }

    .language-list {
        font-size: clamp(16px, 1.5vw, 20px);
    }

    .soft-skills-list {
        font-size: clamp(18px, 2vw, 24px);
    }

    .skill {
        background-color: rgb(172, 199, 172);
        border-radius: 8px;
        width: 50%;
        height: fit-content;
        padding: 3%;
        box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    }

    .skill h3 {
        font-size: clamp(30px, 4vw, 50px);
        color: azure;
        text-align: center;
        margin-bottom: 20px;
    }

    .skill-tree-wrapper {
        width: 100%;
        overflow-x: auto;
    }

    @media (max-width: 1024px) {
        .container {
            flex-direction: column;
            margin: 20px auto;
            gap: 40px;
            padding: 5%;
        }

        .bio, .skill {
            width: 100%;
        }

        .bio h2, .bio h3, .skill h3 {
            text-align: center;
        }

        .language-list, .soft-skills-list {
            display: table;
            margin: 0 auto;
            text-align: left;
        }

        .philosophy-text {
            margin-top: 30px;
        }
    }

    @media (max-width: 480px) {
        .bio-text {
            text-align: left;
        }
    }
</style>
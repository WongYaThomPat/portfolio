<script lang="ts">
    import type { PageProps } from './$types';

    let { data }: PageProps = $props();
    import { fade } from 'svelte/transition';

    const email : string = 'bossthomya@gmail.com'
</script>

<div in:fade={{duration:300}} class='main-container'>
    <div class='img-container'>
        <img  src="/src/lib/images/contact/phonebg.png" alt="phone" style="border-radius:2%">
    </div>
    <div class='link-container'>
        <h1 class='text-5xl' 
            style="margin-bottom: 15px; color:darkseagreen;"
        >
            (In case you like my works...)
        </h1>
        <ul style="line-height: 1.6em;">
            <li style="display: flex; align-items: center; gap: 8px;">
                <img src="/src/lib/images/ico/gmail-svgrepo-com.svg" alt="Email" width="64" height="64" />
                Email / <span>{email}</span>
            </li>
            <li style="display: flex; align-items: center; gap: 8px;">
                <img src="/src/lib/images/ico/github-svgrepo-com.svg" alt="Github" width="64" height="64" />
                Github / 
                <a 
                    href="https://github.com/WongYaThomPat"
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    https://github.com/WongYaThomPat
                </a>
            </li>
        </ul>
    </div>
</div>

<style>
    .main-container {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        gap: 50px;
        padding: 50px;
    }

    .link-container > :not(h1) {
        font-size: 24px;
    }

    .link-container a:hover {
        color: rgb(189, 189, 189);
    }

    .img-container {
        width: 50vw; 
        height: auto;
        background: rgb(217, 235, 204);
        padding: 1%;
        border-radius: 2%;
    }
</style>
<script lang="ts">
    import type { PageProps } from './$types';
    let { data }: PageProps = $props();
    import { fade } from 'svelte/transition';

    const email : string = 'bossthomya@gmail.com'
</script>

<div in:fade={{duration:300}} class='main-container'>
    <div class='img-container'>
        <img src="/src/lib/images/contact/phonebg.png" alt="phone" style="border-radius:2%; width: 100%; height: auto; display: block;">
    </div>
    <div class='link-container'>
        <h1 class='title-text'>
            (In case you like my works...)
        </h1>
        <ul class="contact-list">
            <li>
                <img src="/src/lib/images/ico/gmail-svgrepo-com.svg" alt="Email" width="64" height="64" />
                <div class="contact-text">
                    <strong>Email</strong> <span>{email}</span>
                </div>
            </li>
            <li>
                <img src="/src/lib/images/ico/github-svgrepo-com.svg" alt="Github" width="64" height="64" />
                <div class="contact-text">
                    <strong>Github</strong> 
                    <a 
                        href="https://github.com/WongYaThomPat"
                        target="_blank" 
                        rel="noopener noreferrer"
                    >
                        https://github.com/WongYaThomPat
                    </a>
                </div>
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
        padding: 50px 5vw;
        min-height: 80vh;
    }

    .title-text {
        margin-bottom: 15px; 
        color: darkseagreen;
        font-size: clamp(1.8rem, 4vw, 3rem);
        line-height: 1.2;
    }

    .contact-list {
        list-style: none;
        padding: 0;
        line-height: 1.6em;
    }

    .contact-list li {
        display: flex; 
        align-items: center; 
        gap: 15px;
        margin-bottom: 20px;
    }

    .contact-text {
        display: flex;
        flex-direction: column;
    }

    .link-container > :not(h1) {
        font-size: clamp(16px, 2vw, 24px);
    }

    .link-container a {
        word-break: break-all;
        color: inherit;
        transition: color 0.2s;
    }

    .link-container a:hover {
        color: rgb(189, 189, 189);
    }

    .img-container {
        width: 65vw; 
        max-width: 900px;
        height: auto;
        background: rgb(217, 235, 204);
        padding: 1%;
        border-radius: 2%;
    }

    @media (max-width: 1024px) {
        .main-container {
            flex-direction: column;
            gap: 30px;
            padding: 40px 20px;
            text-align: center;
        }

        .img-container {
            width: 80vw;
        }

        .contact-list li {
            flex-direction: column;
            justify-content: center;
            text-align: center;
        }

        .contact-text {
            align-items: center;
        }
    }
</style>
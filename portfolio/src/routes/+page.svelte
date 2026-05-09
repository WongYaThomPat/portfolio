<script>
    import { fade } from 'svelte/transition';
</script>

<div in:fade>
    <h2 class="portfolio-title">
        Welcome to my Portfolio.
    </h2>
    <p class="instruction">- click on the tabs above to navigate -</p>
</div>

<style>
    div {
        display: flex; 
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        width: 100%;
        min-height: 50vh;
        padding: 10% 5%; 
        box-sizing: border-box;
    }

    .portfolio-title {
        font-size: clamp(2.25rem, 8vw, 3.75rem); 
        line-height: 1;
        font-weight: 700;
    }

    .instruction {
        margin-top: 20px;
        font-size: clamp(0.9rem, 2vw, 1.1rem);
        opacity: 0.8;
    }

    @media (min-width: 768px) {
        div {
            padding: 15%; 
        }
    }
</style>
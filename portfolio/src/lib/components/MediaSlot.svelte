<script lang='ts'>
    import { fly } from 'svelte/transition';

    let { img_links = [] }: { img_links : string[] } = $props();

    let idx = $state(0);
    let direction = $state(1);

    const shift_idx = (dir: -1 | 1) => {
        direction = dir;
        idx += dir;
        if (idx > img_links.length - 1) idx = 0;
        else if (idx < 0) idx = img_links.length - 1;
    };
</script>

{#if img_links.length > 0}
    <div class="carousel-wrapper">
        <div class="carousel-viewport">
            <button class="btn left" onclick={() => shift_idx(-1)}>↤</button>
            <div class="img-wrapper">
                {#key idx}
                    <a href={img_links[idx]} target="_blank" rel="noreferrer">
                        <img 
                            class="thumbnail" 
                            src={img_links[idx]} 
                            alt="Slide {idx + 1}"
                            style="cursor: zoom-in;"
                            in:fly={{ x: direction * 400, duration: 300 }}
                            out:fly={{ x: -direction * 400, duration: 300 }}
                        />
                    </a>
                {/key}
            </div>
            <button class="btn right" onclick={() => shift_idx(1)}>↦</button>
        </div>
        <p>{idx + 1} / {img_links.length}</p>
    </div>
{/if}

<style>
    .carousel-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 10px;
    }

    .carousel-viewport {
        position: relative;
        width: 300px;
        height: 300px;
        overflow: hidden;
        border-radius: 8px;
		gap: 1%;
    }

    .img-wrapper {
        width: 100%;
        height: 100%;
        background-color: rgb(191, 226, 191);
    }

    .thumbnail {
        position: absolute;
        width: 100%;
        height: 100%;
        object-fit: contain;
    }

    .btn {
        position: absolute;
        top: 50%;
		height: 50%;
        transform: translateY(-50%);
        z-index: 10;
        opacity: 0;
        border: none;
        background: rgba(255, 255, 255, 0.5);
        padding: 10px;
        cursor: pointer;
        border-radius: 5px;
        transition: opacity 0.2s ease;
    }

    .left { left: 10px; }
    .right { right: 10px; }

    .carousel-viewport:hover .btn {
        opacity: 1;
    }

</style>
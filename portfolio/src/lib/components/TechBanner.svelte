<script lang='ts'>
    import data from '../json/skill.json';
    const VALID_TOOLS: string[] = data.map(item => item.Tool);
    type Tool = (typeof VALID_TOOLS)[number]

    let { tools } : {tools : Tool[]} = $props();
    const colorMap = Object.fromEntries(data.map(item => [item.Tool, item.Color]));
</script>

<div class='tech-banner'>
    {#each tools as tool}
        <p style="
            background-color: {colorMap[tool] ?? 'grey'};
            padding: 8px;
            color: white;
            border-radius: 8px;
        ">
            {tool}
        </p>    
    {/each}
</div>

<style>
    .tech-banner {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        gap: 8px;
        margin-bottom: 20px;
    }
</style>
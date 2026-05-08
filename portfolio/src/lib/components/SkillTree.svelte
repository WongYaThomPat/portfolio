<script lang='ts'>
    import * as d3 from 'd3';
    import data from '../json/skill.json';

    let grouped = $derived(Object.groupBy(data, item => item.Lang))
    let languages = $derived([...Object.keys(grouped)]);

    let hoveredLang = $state<string | null>(null);

    let containerWidth = $state(900);
    let height = $derived(containerWidth);
    
    let centerX = $derived(containerWidth / 2);
    let centerY = $derived(height / 2);

    let simulation: d3.Simulation<any, undefined>;
    let nodes: any[] = $state([...data]);
    let lastScrollY = 0;

    function draggable(element: SVGElement, d: any) {
        d3.select(element).call(
            d3.drag<SVGElement, any>()
                .on("start", (event) => {
                    if (!event.active) simulation.alphaTarget(0.3).restart();
                    d.fx = d.x;
                    d.fy = d.y;
                })
                .on("drag", (event) => {
                    d.fx = event.x;
                    d.fy = event.y;
                })
                .on("end", (event) => {
                    if (!event.active) simulation.alphaTarget(0);
                    d.fx = null;
                    d.fy = null;
                })
        );
    }

    $effect(() => {
        const handleScroll = () => {
            const currentScrollY = window.scrollY;
            const delta = currentScrollY - lastScrollY;
            lastScrollY = currentScrollY;

            if (simulation) {
                simulation.force("elevator", d3.forceY(delta * 20).strength(0.05));
                simulation.alpha(0.3).restart();
                
                setTimeout(() => {
                    simulation.force("elevator", d3.forceY(0).strength(0.01));
                }, 50);
            }
        };

        window.addEventListener('scroll', handleScroll);
        return () => window.removeEventListener('scroll', handleScroll);
    });

    $effect(() => {
        const scaleFactor = 900 / containerWidth;
    
        simulation = d3.forceSimulation(nodes)
            .force("charge", d3.forceManyBody().strength(-60 * scaleFactor))
            .force("radial", d3.forceRadial(0, centerX, centerY).strength(0.012 * scaleFactor))
            .force("x", d3.forceX(centerX).strength(0.02 * scaleFactor))
            .force("y", d3.forceY(centerY).strength(0.01 * scaleFactor))

        simulation.on("tick", () => {
            nodes = [...nodes];
        });

        return () => simulation.stop();
    });

    $effect(() => {
        if (simulation) {
            const scaleFactor = 900 / containerWidth;
            simulation.force("radial", d3.forceRadial(0, centerX, centerY).strength(0.012 * scaleFactor))
            simulation.force("x", d3.forceX(centerX).strength(0.02 * scaleFactor));
            simulation.force("y", d3.forceY(centerY).strength(0.01 * scaleFactor));
            simulation.alpha(0.3).restart();
        }
    });
</script>

<div class='lang-container' style="color: mintcream;">
    {#each languages as lang}
        <button
            onmouseenter={() => hoveredLang = lang}
            onmouseleave={() => hoveredLang = null}
        >
            {lang}
        </button>      
    {/each}
</div>

<div class='chart-container' bind:clientWidth={containerWidth}>
    <svg width={containerWidth} {height}>
        {#each nodes as node}
            <g>
                <circle
                    use:draggable={node}
                    style="cursor: grab; transition: r 0.2s ease, fill 0.2s ease;"
                    cx={node.x}
                    cy={node.y}
                    r={
                        hoveredLang === null 
                        ? node.Value * (containerWidth < 500 ? 5 : 8) 
                        : (node.Lang === hoveredLang ? node.Value * (containerWidth < 500 ? 12 : 20) : 0)
                    }
                    fill={node.Color}
                />
                
                <text 
                    x={node.x} 
                    y={node.y} 
                    text-anchor="middle" 
                    dominant-baseline="middle"
                    pointer-events="none"
                    style="
                        user-select: none; 
                        font-size: {
                            hoveredLang === null ? (containerWidth < 500 ? 3 : 5) * node.Value
                            : (node.Lang === hoveredLang ? (containerWidth < 500 ? 5 : 8) * node.Value : 0)
                        }px; 
                        fill: white;"
                >
                    {node.Tool} 
                </text>
            </g>
        {/each}
    </svg>
</div>

<style>
    .lang-container {
        margin: 10px 0;
        width: 100%;
        display: flex;
        flex-direction: row;
        justify-content: center;
        flex-wrap: wrap;
        gap: 15px;
    }

    .lang-container button {
        font-size: 16px;
        background: transparent;
        border: none;
        cursor: pointer;
        color: inherit;
        padding: 5px 10px;
    }

    .lang-container button:hover {
        color: rgb(47, 119, 47);
    }

    .chart-container {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        border-radius: 8px;
        overflow: hidden;
    }

    @media (max-width: 600px) {
        .lang-container button {
            font-size: 14px;
        }
    }
</style>
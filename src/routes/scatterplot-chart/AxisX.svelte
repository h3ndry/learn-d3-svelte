<script lang="ts">
	import type { ScaleLinear } from "d3-scale";


    let xTicks = [0, 25, 50, 75, 100];
    export let xScale: ScaleLinear<number, number, never>;
    export let height: number;
    export let width: number;
</script>

<g transform="translate(0, {height})">
    {#each xTicks as tick, index}
        <g class="tick" transform="translate({xScale(tick)}, 0)">
            <line x1="0" x2="0" y1="0" y2="6" stroke="black" />
            <text
                x="0"
                y="6"
                dy="10"
                dominant-baseline="middle"
                text-anchor={index == 0 ? "start" : "middle"}>{tick}%</text
            >
        </g>
    {/each}
    <text x={width} class="axis-title" dy="-6" dominant-baseline="start" text-anchor="end" y="0">
        Final Grade</text
    >
</g>

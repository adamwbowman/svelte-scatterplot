<script lang="ts">
	let bridgeTraffic = [
		{ name: "bridge1", traffic: 58809 },
		{ name: "bridge2", traffic: 54007 },
		{ name: "bridge3", traffic: 86081 },
		{ name: "bridge4", traffic: 91509 },
		{ name: "bridge5", traffic: 280784 },
		{ name: "bridge6", traffic: 87232 },
		{ name: "bridge7", traffic: 109796 },
	]
	
	bridgeTraffic.sort((a,b) => b.traffic - a.traffic)
</script>
	
<svg>
	{#each bridgeTraffic as bridge, index}
		<g transform={`translate(300 ${index * 20})`}>
		<rect width={bridge.traffic / 1000} height="10" fill="red" />
		<text font-size="12" text-anchor="end" dominant-baseline="middle" x="-5" y="5">{bridge.name}</text>
		<text font-size="10" text-anchor="start" dominant-baseline="middle" x="{(bridge.traffic / 1000) +5}" y="5">{bridge.traffic.toLocaleString()}</text>
	</g>
	{/each}
</svg>

<style>
	svg {
		border: 1px solid #ddd;
		width: 100%;
		height: 500px;
		}
</style>
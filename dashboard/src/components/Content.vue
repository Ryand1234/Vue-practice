<template>
	<div id="pagecontent">
		<temp-var-chart :tempVar="tempVar"></temp-var-chart>
		<today-highlight :highlights="highlights"></today-highlight>
	</div>
</template>

<script>
import TempVarChart from './TempVarChart.vue'
import Highlights from './Highlights.vue'
export default {
	props: ['tempVar', 'highlights'],
	components: {
		'temp-var-chart': TempVarChart,
		'today-highlight': Highlights
	}
}
</script>

<style>
#pagecontent {
  border: 1px solid black;
  padding: 2px;
}
</style>
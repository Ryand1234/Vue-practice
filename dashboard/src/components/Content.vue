<template>
	<div id="pagecontent">
		<p>The Child Content are: </p>
		<ul>
			<li v-for="child in child_components" v-bind:key="child">{{child}}</li>
		</ul>
		{{weather_data}}
	</div>
</template>

<script>
export default {
	props: ['weather_data'],
	data(){
		return{
			child_components: ['TempVarChart.vue', 'highlightChart.vue']
		}
	}
}
</script>

<style>
#pagecontent {
  border: 1px solid black;
  padding: 2px;
}
</style>
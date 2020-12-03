<template>
	<div>
		<p>Current Temprature is {{temp}}</p>
	</div>
</template>

<script>
export default {
	props: ['tempVar'],
	data(){ 
		return{
			temp: this.tempVar.current
		}
	}
}
</script>

<style>
	
</style>
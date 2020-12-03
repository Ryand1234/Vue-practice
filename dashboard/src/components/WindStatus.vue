<template>
	<div>
		<p>Today's Wind Status</p>
		<p>Spee: {{speed}}</p>
		<p>Direction: {{direction}}</p>
	</div>
</template>

<script>
export default {
	props: ['windStatus'],
	data(){
		return{
			speed: this.windStatus.speed,
			direction: this.windStatus.direction
		}
	}
}
</script>
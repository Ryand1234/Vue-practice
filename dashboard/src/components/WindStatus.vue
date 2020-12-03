<template>
	<div>
		<p>Wind Speed — {{ speed }}</p>
		<p>Wind Direction — , or {{ direction }} degree clockwise with respect to true N as 0 degree.</p>
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
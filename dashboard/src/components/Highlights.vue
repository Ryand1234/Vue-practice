<template>
	<div>
		<h3>Todays highlights are </h3>
		<uv-index :uvIndex="uvIndex"></uv-index>
		<visibility :visibility="visibility"></visibility>
		<wind-status :windStatus="windStatus"></wind-status>
	</div>
</template>

<script>
import UVIndex from './UVIndex.vue'
import Visibility from './Visibility.vue'
import WindStatus from './WindStatus.vue'

export default {
	props: ['highlights'],
	components: {
		'uv-index': UVIndex,
		'visibility': Visibility,
		'wind-status': WindStatus
	},
	data() {
		return {
			uvIndex: this.highlights.uvindex,
			windStatus: this.highlights.windstatus,
			visibility: this.highlights.visibility
		}
	}
}
</script>
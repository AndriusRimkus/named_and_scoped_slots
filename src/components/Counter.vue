<template>
	<div class="counter-box">
		{{ localCount }}
		<slot name="incPanel" v-bind:inc="inc"></slot>
		<slot name="footer"></slot>
	</div>
</template>

<script>
	export default {

	props: ['initCount'],

	data: function() {
		return {
			localCount: 0
		}
	},

	methods: {
		inc: function() {
			this.localCount++;
		}
	},

	created: function() {
		this.localCount = this.initCount;
	}
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

	.counter-box {
		display: inline-block;
		margin: 0 10px;
		padding: 10px;
		border: 1px solid grey;
	}

</style>
<template>
	<div id="app">
		<Counter v-for="(counter, $index) in counters"
						 v-bind:key="$index"
						 v-bind:initCount="counter.initCount">

		<template slot="incPanel" slot-scope="props">
			<span v-if="counter.type === 'text'"
					v-on:click="props.inc">
					Click me
			</span>

			<span v-if="counter.type === 'image'"
					v-on:click="props.inc">
					<img src="http://via.placeholder.com/50x50" />
			</span>
		</template>

		<hr slot="footer" />

		</Counter>
	</div>
</template>

<script>
	import Counter from './components/Counter.vue'

	export default {
    name: 'app',

		data: function() {
			return {
				counters: [
					{
						initCount: 2,
						type: 'image'
					},
					{
						initCount: 5,
						type: 'text'
					}
				]
			}
		},

		components: {
			Counter
		}
  }
</script>

<style>
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		text-align: center;
		margin-top: 60px;
	}
</style>
<template>
	<div class="hello">
		<h1> Välkommen till Vue demo </h1>
		<p> {{ exempel }} </p>
		<button
			v-show="showButton"
			v-on:click="toggleShowButton"
			v-bind:class="hejsanClass"
			> Hejsan </button>
		<button v-show="!showButton" v-on:click="toggleShowButton"> Jag är osynlig </button>
	</div>
	<div class="">
		<button v-on:click="disableButton"> Stänga av den andra knappen </button>
		<button v-bind:disabled="!buttonIsEnabled"> Klicka mig! </button>
	</div>
	<div class="">
		<div v-for="term in terms" v-bind:key="term.id">
			<strong>{{ term.word }}</strong>:
			{{ term.explanation}}
		</div>
	</div>
</template>

<script>
export default {
	name: 'HelloWorld',
	data: () => ({
		exempel: 'Detta är exempel på en Data Property.',
		showButton: true,
		buttonIsEnabled: true,
		hejsanClass: 'plain',
		terms: [
			{ id: 1, word: 'data property', explanation: 'Variabler i data-objektet' },
			{ id: 2, word: 'template', explanation: 'Där HTML skrivs' },
			{ id: 25, word: 'methods', explanation: 'Där vi skriver metoderna som används i HTML/template' }
		]
	}),
	methods: {
		toggleShowButton() {
			// console.log('Inside handleClick');
			this.showButton = !this.showButton
			this.hejsanClass = 'fancy'
		},
		disableButton() {
			this.buttonIsEnabled = false
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.plain {
	padding: 0.3em 2em;
	border-radius: 0.2em;
}
.fancy {
	padding: 0.5em 3em;
	border-radius: 1em;
	background: hotpink;
}
h3 {
	margin: 40px 0 0;
}
ul {
	list-style-type: none;
	padding: 0;
}
li {
	display: inline-block;
	margin: 0 10px;
}
a {
	color: #42b983;
}
</style>

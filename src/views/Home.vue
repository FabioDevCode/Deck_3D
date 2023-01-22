<template>

	<h1>Deck RPG</h1>

	<section>
		<h2>Choisir un deck</h2>

		<div id="section_deck">
			<div class="presentation_deck" :key="deck.directory" v-for="deck in list_decks">
				<img :src="deck.deck_3d" alt="deck en 3D">
				<h3> {{ deck.name }} </h3>
				<p>
					{{ deck.desc }}
				</p>
				<div class="draws_list">
					<div class="draw" :key="deck.draws.indexOf(draw)" v-for="draw in deck.draws">
						{{ draw }}
					</div>
				</div>
			</div>

		</div>
	</section>

</template>
<!-- T/S -->
<script>
	import { deck_config } from '../assets/data/configDeck.js';

	export default {
		name: 'App',
		data() {
			return {
				list_decks: deck_config,

			}
		},
		methods: {

		}
	};



</script>


<style scoped>
	h1 {
		display: flex;
		justify-content: center;
		align-items: center;
		margin: 50px 0px;
		font-size: 3em;
		color: whitesmoke;
	}

	section {
		border-radius: 8px;
		max-width: 1000px;
		min-width: 320px;
		width: 100%;
		margin: 0 auto;
		background-color: whitesmoke;
		display: flex;
		flex-direction: column;
		align-items: center;
		height: max-content;
	}

	section h2 {
		margin: 20px 0;
		color: black;
	}

	#section_deck {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		flex-shrink: 0;
		max-width: 1200px;
		width: 100%;
		min-width: 320px;
		padding: 25px 5px;
	}

	.presentation_deck {
		cursor: pointer;
		border-radius: 5px;
		background-color: whitesmoke;
		height: 300px;
		width: 240px;
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 15px;
		margin: 0 0 5px 0;
	}

	.presentation_deck:hover {
		background-color: lightgrey;
		box-shadow: 0 0 5px rgba(0, 0, 0, .5);
	}

	.presentation_deck:active {
		transform: scale(.96);
	}

	.presentation_deck img {
		height: auto;
		width: 100px;
		margin-bottom: 20px;
		filter: drop-shadow(0px 10px 10px rgba(0, 0, 0, .2));
	}

	.presentation_deck h3 {
		text-align: center;
		color: black;
		margin-bottom: 10px;
	}

	.presentation_deck p {
		text-align: center;
		color: black;
		font-style: italic;
		display: inline-block;
		margin-bottom: 10px;
	}

	.draws_list {
		display: flex;
	}

	.draw {
		border-radius: 5px;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: black;
		color: white;
		height: 25px;
		width: 25px;
		margin: 0 5px;
	}

</style>
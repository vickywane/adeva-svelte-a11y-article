<script context="module" >
	import "../assets/index.css"
	import Data from '../data.json'
	import Header from '../components/header.svelte'

	const data =    {
				"id": "1",
				"name": "Ada Lovelace",
				"died": "1999 - 1999",
				"img_uri" : "https://res.cloudinary.com/dkfptto8m/image/upload/v1620003312/wordpress/ada-removebg-preview.png",
				"description":"Ada Lovelace was an English mathematician and the world’s first computer programmer. Lovelace was born into privilege as the daughter of a famously unstable romantic poet, Lord Byron (who left her family when Ada was just 2 months old) and Lady Wentworth.",
				"achievements" : "Computer Programming"
			}

	export async function preload(page, session) {
		const { about } = page.params;

		// find single heroine by name
		const Heroine =  Data.heroes.find(({ name }) =>  name === about )
		console.log(Heroine)
		return Heroine
	}
</script>

<script>
	export let Heroine;
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<div class="App" style="height: 100vh; color: #fff" >
	<Header />
	<div class="align-center" >
		<div style="width: 40rem;">
			<div class="align-center" >
				<img alt={data.name}
					 class="img"
					 src={data.img_uri}/>
			</div>
			<br />
			<h3 style="text-align: center" > {data.name}</h3>

			<p>
			<b>	Died</b>: {data.died}
			</p>
			<p> Heroine: {JSON.stringify(Heroine)} </p>
			<p>
				<b>Achievements </b>: {data.achievements}
			</p>

			<p>
				{data.description}
			</p>
			<br />

			<div class={"align-center"}>
				<button
						class="custom-btn"
				>
					Read Wiki Page
				</button>
			</div>
		</div>
	</div>
</div>
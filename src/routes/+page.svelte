<script lang="ts">
	import { links } from '$lib/socials.json';
	import PhoneScreen from './PhoneScreen.svelte';
	import ProjectCard from './ProjectCard.svelte';
</script>

<h1>NaiPofo</h1>
<div class="main-socials">
	{#each links as { name, href, icon, nick }}
		<a {href}>
			<img src={'icons/' + icon} alt="" />
			<div class="label">
				<span class="nick">{nick}</span>
				<span class="name">{name}</span>
			</div>
		</a>
	{/each}
</div>
<PhoneScreen text={'hello...           \nthis site is not done yet, please check it out later!'} />

<ProjectCard title="Yomishi">
	<p>Pop-up dictonary for browsers, phones and anki. It's still <b>under development</b>.</p>
</ProjectCard>

<ProjectCard title="UtaViewer">
	<p>Android application written in Kotlin that displays song lyrics.</p>
</ProjectCard>

<ProjectCard title="Flying Currency Converter">
	<p>Currency converter that includes historical conversion graphs and the price of gold.</p>
</ProjectCard>

<ProjectCard title="Boxey System" github="boxey">
	<p>
		Package delivery and tracking system that is still <b>under development</b>.
	</p>
</ProjectCard>

<ProjectCard title="Web Lab" github="weblabs">
	<p>A statically generated website about unique web technologies.</p>
</ProjectCard>

<ProjectCard title="BiedBot">
	<p>Telegram bot that automatically generates promo codes for a popular grocery store chain.</p>
</ProjectCard>

<ProjectCard title="Vin Watcher">
	<p>Telegram bot for scraping and tracking offers on a popular online clothes retailer.</p>
</ProjectCard>

<ProjectCard title="Telegram Pixabay Bot" github="openPixabayBot">
	<p>Telegram bot for searching and retriving images from the Pixabay image library.</p>
</ProjectCard>

<ProjectCard title="Anki JetMap">
	<p>Dart CLI app that converts jetpunk quizes into anki flashcards.</p>
</ProjectCard>

<style lang="scss">
	:global(body) {
		color: white;
		background-color: black;
		display: flex;
		flex-direction: column;
		align-items: center;
		font-family: monospace;
	}

	h1 {
		filter: url('filters.svg#glitchy-text');
		font: Min(20vw, 7rem) 'Times New Roman', serif;
		margin-bottom: 0;
	}
	.main-socials {
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		font: 1.2rem 'Roboto Mono', monospace;
		width: Min(400px, 100vw);

		a {
			padding: 8px;

			$glow: drop-shadow(0 0 6px #00ffff) drop-shadow(0 0 2px #00ffff88);

			&:hover {
				img {
					transform: scale(1.3);
					filter: $glow;
				}

				.label {
					opacity: 1;
				}
			}

			img {
				transition: transform 0.3s;
			}

			.label {
				text-align: center;
				display: flex;
				flex-direction: column;
				position: absolute;
				left: 0;
				right: 0;
				opacity: 0;
				transition: opacity 0.3s;
				pointer-events: none;
				filter: $glow drop-shadow(0 0 6px #000000) drop-shadow(0 0 2px #000000);
				color: white;

				.nick {
					font-size: 1.4rem;
				}

				.name {
					font-size: 1rem;
				}
			}
		}

		img {
			width: 48px;
			height: 48px;
		}
	}
</style>

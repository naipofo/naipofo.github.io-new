<script lang="ts">
	import { links } from '$lib/socials.json';
	import PhoneScreen from './PhoneScreen.svelte';
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

<PhoneScreen>
	----hello----<br />this site is not done yet, please check it out later!
</PhoneScreen>

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

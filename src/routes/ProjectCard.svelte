<script lang="ts">
	export let title: string;
	export let github: string | undefined = undefined;
	$: githubLink = `https://github.com/naipofo/${github ?? title.replaceAll(' ', '')}`;
</script>

<article>
	<header>
		<h3>{title}</h3>
		<a href={githubLink} class="github">github</a>
	</header>
	<main>
		<slot />
	</main>
</article>

<style>
	article {
		border: 1px solid gray;
		margin-bottom: 16px;
		width: min(650px, 90vw);
	}
	header {
		display: flex;
	}
	h3 {
		flex-grow: 1;
	}
	
</style>

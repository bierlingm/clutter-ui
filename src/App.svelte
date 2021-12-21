<script lang="ts">
	import Page from "./stories/Page.svelte"
</script>

<body>
	<main>
		<Page/>
	</main>
</body>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
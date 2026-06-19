<script>
	import ServiceCard from './ServiceCard.svelte';
	import { services } from '$lib/data/content.js';
</script>

<section class="services">
	<div class="services__grid">
		{#each services as service}
			<ServiceCard {service} />
		{/each}
	</div>
</section>
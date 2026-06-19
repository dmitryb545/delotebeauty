<script lang="ts">
	let activeFilter = $state('all');

	const filters = [
		{ id: 'all', label: 'All' },
		{ id: 'hair', label: 'Hair' },
		{ id: 'makeup', label: 'Makeup' }
	];

	const works = [
		{ image: '/img/work-1.png', category: 'brows' },
		{ image: '/img/work-2.png', category: 'makeup' },
		{ image: '/img/work-3.png', category: 'nails' },
		{ image: '/img/work-4.png', category: 'makeup' },
		{ image: '/img/work-5.png', category: 'hair' }
	];

	const filteredWorks = $derived(
		activeFilter === 'all'
			? works
			: works.filter(w => w.category === activeFilter)
	);
</script>

<section class="works">
<div class="container">
	<div class="works__title">
		<h2>Our Works</h2>
	</div>

	<div class="works__filters">
		{#each filters as filter}
			<button
				class="filter-btn"
				class:active={activeFilter === filter.id}
				onclick={() => activeFilter = filter.id}
			>
				{filter.label}
			</button>
		{/each}
	</div>

	<div class="works__grid">
		{#each filteredWorks as work}
			<div class="work-item">
				<img src={work.image} alt="" />
			</div>
		{/each}
	</div>
	</div>
</section>
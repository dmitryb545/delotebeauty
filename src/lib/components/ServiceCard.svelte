<script lang="ts">
	type Service = {
		title: string;
		image: string;
	};

	const { service }: { service: Service } = $props();
</script>

<div class="service-card">
	<img src={service.image} alt={service.title} />
	<p>{service.title}</p>
</div>
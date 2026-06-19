<script lang="ts">
	let menuOpen = $state(false);

	function openMenu() {
		menuOpen = true;
	}

	function closeMenu() {
		menuOpen = false;
	}
</script>

<header>
	<div class="container">
		{#if !menuOpen}
			<button
				class="burger"
				on:click={openMenu}
				aria-label="Open Menu"
			>
				☰
			</button>
		{/if}

		<!-- Крестик -->
		{#if menuOpen}
			<button
				class="close"
				on:click={closeMenu}
				aria-label="Close Menu"
			>
				✕
			</button>
		{/if}

		<nav class="navbar">

			<div class:active={menuOpen} class="menu-left">
				<a href="/">Home</a>
				<a href="/masters">Masters</a>
				<a href="/cosmetics">Cosmetics</a>
			</div>

			<div class="navbar-center">
				<img src="/svg/omega-sign-svgrepo-com 1.svg" alt="logo" />
			</div>

			<div class:active={menuOpen} class="menu-right">
				<a href="/action">Action</a>
				<a href="/review">Review</a>
				<a href="/contacts">Contacts</a>
			</div>

		</nav>

		{#if menuOpen}
			<div class="overlay active" on:click={closeMenu}></div>
		{/if}

	</div>
</header>
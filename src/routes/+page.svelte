<script>
	// Sample house data - you can replace this with real data from an API or database
	let houses = [
		{
			id: 1,
			title: 'Fedora 42 Cloud Edition',
			price: '$450,000',
			image: 'k1.png',
			location: ''
		},
		{
			id: 2,
			title: 'CentOS 6',
			price: '$280,000',
			image: 'k2.png',
			location: ''
		},
		{
			id: 3,
			title: 'Debian 12',
			price: '$320,000',
			image: 'https://images.unsplash.com/photo-1512917774080-9991f1c4c750?w=400&h=300&fit=crop',
			location: ''
		}
	];

	function handleBuyClick(house) {
		window.open('https://www.youtube.com/watch?v=dQw4w9WgXcQ', '_blank');
	}
</script>

<svelte:head>
	<title>Containers for Sale - Premium Real Estate</title>
	<meta name="description" content="Browse our collection of premium containers for sale" />
</svelte:head>

<nav class="navbar">
	<div class="nav-container">
		<div class="nav-logo">
			<img src="/docker-emlak-logo.svg" alt="Docker Emlak" />
		</div>
		<div class="nav-links">
			<a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ" class="nav-link">Containers</a>
			<a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ" class="nav-link">About</a>
			<a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ" class="nav-link">Contact</a>
		</div>
	</div>
</nav>

<div class="container">
	<header class="header">
		<h1>Premium Containers for Sale</h1>
		<p>Find your dream container from our curated collection</p>
	</header>

	<div class="houses-grid">
		{#each houses as house (house.id)}
			<div class="house-card">
				<div class="image-container">
					<img src={house.image} alt={house.title} />
					<div class="price-badge">{house.price}</div>
				</div>

				<div class="card-content">
					<h3 class="house-title">{house.title}</h3>
					<p class="location">{house.location}</p>

					<button class="buy-button" on:click={() => handleBuyClick(house)}> Buy Now </button>
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.navbar {
		background: white;
		box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
		position: sticky;
		top: 0;
		z-index: 100;
		margin-bottom: 2rem;
	}

	.nav-container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 1rem;
		display: flex;
		justify-content: space-between;
		align-items: center;
		height: 70px;
	}

	.nav-logo img {
		height: 40px;
		width: auto;
	}

	.nav-links {
		display: flex;
		gap: 2rem;
	}

	.nav-link {
		text-decoration: none;
		color: #2c3e50;
		font-weight: 500;
		transition: color 0.3s ease;
	}

	.nav-link:hover {
		color: #3498db;
	}

	.container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 2rem 1rem;
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
	}

	.header {
		text-align: center;
		margin-bottom: 3rem;
	}

	.header h1 {
		font-size: 2.5rem;
		color: #2c3e50;
		margin-bottom: 0.5rem;
		font-weight: 700;
	}

	.header p {
		font-size: 1.2rem;
		color: #7f8c8d;
		margin: 0;
	}

	.houses-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
		gap: 2rem;
		margin-bottom: 2rem;
	}

	.house-card {
		background: white;
		border-radius: 12px;
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
		overflow: hidden;
		transition:
			transform 0.3s ease,
			box-shadow 0.3s ease;
	}

	.house-card:hover {
		transform: translateY(-5px);
		box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15);
	}

	.image-container {
		position: relative;
		height: 250px;
		overflow: hidden;
	}

	.image-container img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		transition: transform 0.3s ease;
	}

	.house-card:hover .image-container img {
		transform: scale(1.05);
	}

	.price-badge {
		position: absolute;
		top: 1rem;
		right: 1rem;
		background: #e74c3c;
		color: white;
		padding: 0.5rem 1rem;
		border-radius: 25px;
		font-weight: bold;
		font-size: 1.1rem;
		box-shadow: 0 2px 10px rgba(231, 76, 60, 0.3);
	}

	.card-content {
		padding: 1.5rem;
	}

	.house-title {
		font-size: 1.4rem;
		color: #2c3e50;
		margin-bottom: 0.5rem;
		font-weight: 600;
	}

	.location {
		color: #7f8c8d;
		margin-bottom: 1rem;
		font-size: 1rem;
	}

	.buy-button {
		width: 100%;
		background: linear-gradient(135deg, #3498db, #2980b9);
		color: white;
		border: none;
		padding: 1rem 2rem;
		border-radius: 8px;
		font-size: 1.1rem;
		font-weight: 600;
		cursor: pointer;
		transition: all 0.3s ease;
		text-transform: uppercase;
		letter-spacing: 0.5px;
	}

	.buy-button:hover {
		background: linear-gradient(135deg, #2980b9, #1f639a);
		transform: translateY(-2px);
		box-shadow: 0 4px 15px rgba(52, 152, 219, 0.4);
	}

	.buy-button:active {
		transform: translateY(0);
	}

	/* Responsive design */
	@media (max-width: 768px) {
		.houses-grid {
			grid-template-columns: 1fr;
		}

		.header h1 {
			font-size: 2rem;
		}

		.container {
			padding: 1rem;
		}

		.nav-links {
			gap: 1rem;
		}

		.nav-link {
			font-size: 0.9rem;
		}
	}

	@media (max-width: 480px) {
		.houses-grid {
			grid-template-columns: 1fr;
			gap: 1rem;
		}

		.price-badge {
			font-size: 0.9rem;
			padding: 0.4rem 0.8rem;
		}

		.image-container {
			height: 200px;
		}
	}
</style>

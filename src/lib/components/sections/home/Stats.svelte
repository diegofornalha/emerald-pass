<script>
	import { Section, Container } from "$lib/components/atoms/index";

	let stats = [
		{
			number: "1,000",
			title: "Projects",
			description: "Over 100 communities use Emerald City on Flow.",
		},
		{
			number: "1,000",
			title: "Projects",
			description: "Over 100 communities use Emerald City on Flow.",
		},
		{
			number: "1,000",
			title: "Projects",
			description: "Over 100 communities use Emerald City on Flow.",
		},
	];
</script>

<div>
	<Section>
		<Container class="width-large">
			<div class="intro">
				<h2>Emerald City is huge.</h2>
				<p>
					Emerald City has built main stream products on Flow such as FLOAT,
					which consistently more used than NBATopShot.
				</p>
			</div>
			<div class="stats-container">
				{#each stats as stat}
					<div class="stat-container">
						<h2>{stat.number}</h2>
						<h3>{stat.title}</h3>
						<p>{stat.description}</p>
					</div>
				{/each}
			</div>
		</Container>
	</Section>
</div>

<style type="scss">
	@use "../../../styles/abstracts" as *;

	.intro {
		margin-left: auto;
		margin-right: auto;
		max-width: 600px;

		h2 {
			font-weight: 700;
			font-size: 40px;
			line-height: 46px;
			text-align: center;
			margin-bottom: 16px;
		}

		p {
			font-weight: 300;
			font-size: 16px;
			line-height: 24px;
			text-align: center;
		}
	}

	.stats-container {
		margin-top: 40px;
		display: grid;
		width: 100%;
		grid-template-columns: repeat(3, minmax(0, 1fr));
		gap: 40px;

		@media all and (max-width: 1000px) {
			grid-template-columns: repeat(2, minmax(0, 1fr));
		}

		@media all and (max-width: 700px) {
			grid-template-columns: repeat(1, minmax(0, 1fr));
		}
	}

	.stat-container {
		h2 {
			font-weight: 700;
			font-size: 40px;
			line-height: 46px;
			color: var(--clr-primary-main-t1);
		}

		h3 {
			text-transform: uppercase;
			font-weight: 800;
			font-size: 16px;
			margin-top: 10px;
		}

		p {
			margin-top: 10px;
			font-size: 16px;
		}
	}
</style>

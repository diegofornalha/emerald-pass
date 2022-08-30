<script>
	import { Section, Container } from "$lib/components/atoms/index";

	let benefits = [
		{
			title: "FLOAT",
			points: ["Access to Challenges feature"],
			image: "float.png",
		},
		{
			title: "Touchstone",
			points: [
				"Your own custom URL",
				"Add to NFT Catalog with 1 click",
				"Airdrop to a batch of users",
			],
			image: "touchstone.png",
		},
		{
			title: "Emerald bot",
			points: ["Setup a custom verifier for your Discord"],
			image: "emerald-bot.png",
		},
		{
			title: "Toucans",
			points: [
				"Your own custom URL",
				"Add to NFT Catalog with 1 click",
				"Airdrop to a batch of users",
			],
			image: "toucans.jpeg",
		},
		{
			title: "Geeft",
			points: ["Add your collection to our gifting platform"],
			image: "geeft.png",
		},
		{
			title: "Emerald Academy",
			points: [
				"Receive discounts on paid courses/bootcamps",
				"Access to Achievements page",
			],
			image: "emerald-academy.png",
		},
	];
</script>

<div class="background-color" id="benefits">
	<Section>
		<Container class="width-large">
			<div class="main-section">
				<div>
					<h2>Get exclusive access to our benefits</h2>
					<p>
						As an Emerald Pass subscriber, you will be able to get premium
						features and abilities on all of our products, including some
						educational material.
					</p>
				</div>
				<div class="benefits">
					{#each benefits as benefit}
						<div class="benefit">
							<img src={`/images/project-logos/${benefit.image}`} alt="logo" />
							<div class="benefit-description">
								<h3>{benefit.title}</h3>
								<ul>
									{#each benefit.points as point}
										<li>{point}</li>
									{/each}
								</ul>
							</div>
						</div>
					{/each}
				</div>
			</div>
		</Container>
	</Section>
</div>

<style type="scss">
	@use "../../../styles/abstracts" as *;

	.background-color {
		background-color: var(--clr-primary-main-t8);
	}

	.main-section {
		gap: 40px;
		display: grid;
		grid-template-columns: repeat(3, minmax(0, 1fr));

		.benefits {
			display: grid;
			grid-column: span 2 / span 2;
			gap: 40px;
			grid-template-columns: repeat(2, minmax(0, 1fr));

			.benefit {
				align-items: flex-start;
				display: flex;

				img {
					position: relative;
					width: 65px;
					height: 65px;
					display: block;
				}

				.benefit-description {
					align-items: flex-start;
					flex-direction: column;
					display: flex;
					margin-left: 10px;

					h3 {
						white-space: nowrap;
						font-size: 22px;
						line-height: 28px;
					}

					li {
						font-size: 16px;
						line-height: 24px;
					}

					ul {
						padding-left: 15px;
						margin-top: 0px;
					}
				}
			}
		}

		h2 {
			font-weight: 700;
			font-size: 40px;
			line-height: 46px;
			color: var(--clr-primary-main-t1);
		}

		p {
			margin-top: 10px;
			font-size: 16px;
		}
	}
</style>

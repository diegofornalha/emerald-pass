<script>
	import {
		Section,
		Container,
		Button,
		AdaptableGrid,
		Marquee,
		Stack,
		TouchstoneIcon,
	} from "$lib/components/atoms/index";
</script>

<div class="background">
	<Section>
		<Container class="width-large">
			<AdaptableGrid>
				<Stack align="start">
					<h1>Emerald City's Premium Pass</h1>
					<p>
						Emerald Pass allows you to gain access to tons of premium features
						across all of our products, all under one subscription. See below
						for
						<a href="#benefits">subscriber benefits</a>,
						<a href="/purchase">purchasing</a>, and more.
					</p>
					<Button href="/purchase" rightIcon="arrow-forward-circle"
						>PURCHASE</Button>
					<div class="heading-info">
						<p><strong>Going live soon</strong></p>
						<p>
							Starting on October 15th, you will be able to purchase Emerald
							Pass and enjoy all the benefits it offers.
						</p>
					</div>
				</Stack>
				<Stack align="center" justify="center">
					<video width="100%" height="100%" autoplay loop muted>
						<source src="emerald1.webm" type="video/webm" />
						<track kind="captions" />
						Your browser does not support the video tag.
					</video>
				</Stack>
			</AdaptableGrid>
		</Container>
	</Section>
</div>
<Marquee repeat={10}>
	<div class="marquee-element">
		<span>CREATED WITH 💜 BY&nbsp;</span> EMERALD CITY DAO
	</div>
	<div class="marquee-element emerald-wrapper">
		<TouchstoneIcon />
	</div>
</Marquee>

<style type="scss">
	a {
		text-decoration: none;
	}
	.heading-info {
		padding: 24px;
		border-radius: 0.75rem;
		background-color: var(--clr-primary-main-t8);
	}

	h1 {
		font-size: var(--fs-700);
		font-weight: 900;

		span {
			color: var(--clr-primary-main);
		}
	}

	p {
		font-size: 16px;
	}

	.marquee-element {
		display: flex;
		align-items: center;
		justify-content: center;
		margin-inline: 3rem;
		letter-spacing: 0.3em;
		font-size: var(--fs-200);
		padding-block: 0.4rem;
		font-weight: 500;

		span {
			font-style: italic;
		}
	}

	.background {
		background: radial-gradient(
			ellipse at right,
			var(--clr-primary-main-t8),
			transparent
		);
		backdrop-filter: blur(50px);
	}
</style>

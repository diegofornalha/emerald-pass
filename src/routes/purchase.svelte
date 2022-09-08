<script>
	import { user } from "$stores/FlowStore.js";
	import Container from "$lib/components/atoms/Container.svelte";
	import Section from "$lib/components/atoms/Section.svelte";
	import { purchaseEmeraldPass, timeOnEmeraldPass } from "$flow/actions.js";
	import WalletConnectModal from "$lib/components/atoms/WalletConnectModal.svelte";
	import Button from "$lib/components/atoms/Button.svelte";
	import Countdown from "$lib/components/utility/Countdown.svelte";
	import TransactionModal from "$lib/components/atoms/TransactionModal.svelte";
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<TransactionModal />
{#if $user?.loggedIn}
	<Section>
		<Container>
			<div class="top">
				{#await timeOnEmeraldPass($user.addr) then endingTime}
					<p>You have</p>
					{#if !endingTime || endingTime <= Date.now() / 1000}
						<h3>00:00:00</h3>
					{:else}
						<h3><Countdown unix={endingTime} /></h3>
					{/if}
					<p>left on your subscription.</p>
				{/await}
			</div>

			<div class="box">
				<h4>Add more time by purchasing below</h4>
				<div class="purchase-options">
					<div class="option">
						<h2>1 Month</h2>
						<h5>100 $FUSD</h5>
						<p>Add a month long of Emerald Pass benefits.</p>
						<span class="line" />
						<Button on:click={() => purchaseEmeraldPass("2629743.0", "100.0")}
							>Purchase</Button>
					</div>
					<div class="option special-border">
						<h2>1 Year</h2>
						<h5>1000 $FUSD</h5>
						<p>Add a year long of Emerald Pass benefits.</p>
						<span class="line" />
						<Button on:click={() => purchaseEmeraldPass("31556926.0", "1000.0")}
							>Purchase</Button>
					</div>
				</div>
			</div>
		</Container>
	</Section>
{:else}
	<WalletConnectModal />
{/if}

<style type="scss">
	@use "../lib/styles/abstracts" as *;

	.top {
		text-align: center;
		margin: 0;

		p,
		h3 {
			margin: 0;
		}
	}

	.box {
		background-color: var(--clr-primary-main-t8);
		padding: 50px;
		margin-top: 100px;
		border-radius: 24px;

		h4 {
			text-align: center;
		}

		.purchase-options {
			position: relative;
			display: grid;
			grid-template-columns: repeat(2, minmax(0, 1fr));
			gap: 50px;
			margin-top: 50px;

			@media all and (max-width: 700px) {
				grid-template-columns: repeat(1, minmax(0, 1fr));
			}

			.special-border {
				border: 3px dotted;
				border-color: var(--clr-primary-main-t2);
			}

			.option {
				position: relative;
				background-color: var(--clr-primary-main-t8);
				padding: 24px;
				border-radius: 0.75rem;

				h2 {
					font-weight: 700;
					font-size: 40px;
					line-height: 46px;
				}

				h5 {
					margin: 0px;
					color: var(--clr-font-heading);
					margin-top: 5px;
				}

				p {
					margin-top: 10px;
					font-size: 16px;
				}

				.line {
					position: relative;
					display: block;
					width: 100%;
					height: 2px;
					background-color: var(--clr-primary-main-t8);
					margin-top: 10px;
					margin-bottom: 10px;
				}
			}
		}
	}
</style>

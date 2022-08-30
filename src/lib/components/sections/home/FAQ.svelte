<script>
	import { Section, Container } from "$lib/components/atoms/index";

	let questions = [
		{
			title: "What is this pass for?",
			answer: "It is an awesome pass, I swear to god!",
		},
		{
			title: "What is this pass for?",
			answer: "It is an awesome pass, I swear to god!",
		},
		{
			title: "What is this pass for?",
			answer: "It is an awesome pass, I swear to god!",
		},
		{
			title: "What is this pass for?",
			answer: "It is an awesome pass, I swear to god!",
		},
		{
			title: "What is this pass for?",
			answer: "It is an awesome pass, I swear to god!",
		},
	];
</script>

<div id="faq">
	<Section>
		<Container class="width-large">
			<div class="main-section">
				<h2>Frequently Asked Questions</h2>
				{#each questions as question}
					<div class="question">
						<div class="question-description">
							<h3>{question.title}</h3>
							<p>{question.answer}</p>
						</div>
					</div>
				{/each}
			</div>
		</Container>
	</Section>
</div>

<style type="scss">
	@use "../../../styles/abstracts" as *;

	.main-section {
		gap: 40px;
		display: grid;
		grid-template-columns: repeat(3, minmax(0, 1fr));

		@media all and (max-width: 1000px) {
			grid-template-columns: repeat(2, minmax(0, 1fr));
		}

		@media all and (max-width: 700px) {
			grid-template-columns: repeat(1, minmax(0, 1fr));
		}

		.question {
			align-items: flex-start;
			display: flex;

			.question-description {
				align-items: flex-start;
				flex-direction: column;
				display: flex;
				margin-left: 10px;

				h3 {
					white-space: nowrap;
					font-size: 22px;
					line-height: 28px;
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

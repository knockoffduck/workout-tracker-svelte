<script>
	import AddExerciseForm from "./AddExerciseForm.svelte";

	const exercises = [];

	function addExercise(exercise) {
		exercises.push({
			title: exercise,
			completed: false,
		});

		exercises = exercises;
	}
</script>

<main>
	<AddExerciseForm {addExercise} />
	<ul>
		{#each exercises as exercise}
			<li
				class:doneon:click={() =>
					(exercise.completed = !exercise.completed)}
			>
				{exercise.title}
			</li>
		{/each}
	</ul>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	.done {
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

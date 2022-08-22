<script>
    export let addExercise;

    let newExercise = "";

    function formSubmitted() {
        addExercise(newExercise);
        newExercise = "";
    }
</script>

<form on:submit|preventDefault={formSubmitted}>
    <h2>Workout Routine</h2>
    <label>
        <input bind:value={newExercise} placeholder="Enter an Exercise..." />
    </label>
    <button>Add Exercise</button>
</form>

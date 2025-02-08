<script>
    let symptoms = [];
    let disease = "";
    let suggestions = [];

    function detectDisease() {
        if (symptoms.includes("diarrhea") && symptoms.includes("vomiting")) {
            disease = "Food Poisoning";
            suggestions = ["Drink plenty of fluids", "Avoid solid food", "Rest"];
        } else if (symptoms.includes("headache") && symptoms.includes("fatigue")) {
            disease = "Migraine";
            suggestions = ["Rest in a dark room", "Stay hydrated", "Take pain relievers"];
        } else if (symptoms.includes("rash") && symptoms.includes("fatigue")) {
            disease = "Allergic Reaction";
            suggestions = ["Avoid allergens", "Apply anti-itch cream", "Consult a doctor if severe"];
        } else {
            disease = "Unknown Condition";
            suggestions = ["Consult a doctor", "Monitor symptoms", "Stay hydrated"];
        }
    }

    function submitSymptoms(event) {
        event.preventDefault();
        detectDisease();
    }
</script>

<div class="container">
    <div class="content">
        <h2 class="h2">Symptom Detector</h2>
        <h3>Select your symptoms:</h3>

        <div class="symptom-list">
            {#each ["diarrhea", "vomiting", "headache", "fatigue", "rash"] as symptom}
                <label class="symptom-option">
                    <input type="checkbox" value={symptom} bind:group={symptoms} />
                    {symptom.charAt(0).toUpperCase() + symptom.slice(1)}
                </label>
            {/each}
        </div>

        <button class="btn" on:click={submitSymptoms}>Submit</button>

        {#if disease}
            <div class="result">
                <h3>You may have <span class="highlight">{disease}</span>.</h3>
                <p>Please follow these suggestions:</p>
                <ul>
                    {#each suggestions as suggestion}
                        <li>{suggestion}</li>
                    {/each}
                </ul>
            </div>
        {/if}
    </div>
</div>

<style lang="postcss">
    .container {
        @apply flex justify-center items-center h-full;
        margin-left: 150px; /* Moves the content slightly to the right */
    }
    .content {
        @apply space-y-6 text-center flex flex-col items-center bg-white p-8 rounded-lg shadow-lg w-96;
        color: black; /* Ensures all text is black */
    }
    .symptom-list {
        @apply flex flex-col space-y-3;
    }
    .symptom-option {
        @apply flex items-center space-x-2 text-lg text-black;
    }
    .btn {
        @apply bg-blue-500 text-white p-2 rounded-md w-full cursor-pointer hover:bg-blue-600 transition;
    }
    .result {
        @apply mt-4 text-lg text-black;
    }
    .highlight {
        @apply text-blue-600 font-semibold;
    }
</style>

<script>
    let symptoms = [];
    let disease = "";
    let suggestions = [];

    function detectDisease() {
        if (symptoms.includes("fever") && symptoms.includes("cough") && symptoms.includes("shortness of breath")) {
            disease = "Legionnaires' disease";
            suggestions = ["Seek medical attention immediately", "Get plenty of rest", "Stay hydrated"];
        } else if (symptoms.includes("diarrhea") && symptoms.includes("abdominal cramps") && symptoms.includes("weight loss")) {
            disease = "Giardiasis (C)";
            suggestions = ["Drink plenty of fluids", "Avoid fatty or greasy foods", "Take medication as prescribed by your doctor"];
        } else if (symptoms.includes("diarrhea") && symptoms.includes("stomach cramps") && symptoms.includes("loss of appetite")) {
            disease = "Cryptosporidiosis (C)";
            suggestions = ["Drink plenty of fluids", "Avoid close contact with others", "Take medication as prescribed by your doctor"];
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
            {#each ["fever", "cough", "shortness of breath", "diarrhea", "abdominal cramps", "weight loss", "stomach cramps", "loss of appetite"] as symptom}
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
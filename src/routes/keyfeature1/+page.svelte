<script>
    let pH = '';
    let hardness = '';
    let solids = '';
    let chloramines = '';
    let sulfates = '';

    let prediction = '';

    function submitData() {
        // Handle form submission here
        console.log('pH:', pH);
        console.log('Hardness:', hardness);
        console.log('Solids:', solids);
        console.log('Chloramines:', chloramines);
        console.log('Sulfates:', sulfates);

        const data = {
            inputs: {
                ph: Number(pH),
                Hardness: Number(hardness),
                Solids: Number(solids),
                Chloramines: Number(chloramines),
                Sulfate: Number(sulfates)
            }
        };

        fetch('http://127.0.0.1:5000/predict', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify(data)
        })
            .then(response => response.json())
            .then(data => {prediction = data.prediction; console.log(data)})
            .catch(error => console.error(error));
    }
</script>

<div class="container h-full mx-auto flex justify-center items-center">
    <div class="space-y-10 text-center flex flex-col items-center">
        <h2 class="h2">Water Potability AI Analyzer</h2>
        <h3> Enter the following values in numerical input:</h3>
        <div class="flex flex-col space-y-4 w-80">
            <input type="text" placeholder="pH" class="input-field p-2 border rounded-md text-black" bind:value={pH} />
            <input type="text" placeholder="Hardness" class="input-field p-2 border rounded-md text-black" bind:value={hardness} />
            <input type="text" placeholder="Solids" class="input-field p-2 border rounded-md text-black" bind:value={solids} />
            <input type="text" placeholder="Chloramines" class="input-field p-2 border rounded-md text-black" bind:value={chloramines} />
            <input type="text" placeholder="Sulfates" class="input-field p-2 border rounded-md text-black" bind:value={sulfates} />
            <button class="btn variant-filled w-full p-2 rounded-md" on:click={submitData}>Submit</button>
        <div class="mt-4">
            <p class="text-lg">
                {#if prediction === "0"}
                    Water quality is bad maybe you should check the community outbreaks and alerts to see if there is any bad water in your area or not. You should take the right protocals to prevent yourself from any waterborne diseases
                {:else if prediction === "1"}
                    Water quality is good and you should be fine. You can always check the community outbreaks and alerts to see if there is any bad water in your area or not. You should take the right protocals to prevent yourself
                {/if}
            </p>
        </div>

        </div>
    </div>
</div>

<style lang="postcss">
    .container {
        @apply flex justify-center items-center h-full;
    }
    .input-field {
        @apply p-2 border rounded-md text-black;
    }
    .btn {
        @apply variant-filled w-full p-2 rounded-md;
    }
</style>
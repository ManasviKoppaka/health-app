<script>
    import { onMount } from 'svelte';
    let alerts = [];

    const locations = [
        "Central Park",
        "Times Square",
        "Rockefeller Center",
        "Madison Square Garden"
    ];

    function getRandomLocation() {
        return locations[Math.floor(Math.random() * locations.length)];
    }

    function getCurrentTime() {
        const now = new Date();
        return now.toLocaleString();
    }

    onMount(() => {
        alerts = Array.from({ length: 3 }, (_, i) => ({
            id: i + 1,
            message: `Be Careful, water in ${getRandomLocation()} is bad`,
            time: getCurrentTime()
        }));
    });
</script>

<style>
    .alert {
        background-color: #ffcccb;
        color: black;
        padding: 10px;
        margin: 10px 0;
        border: 1px solid red;
        border-radius: 5px;
    }

    .info-section {
        margin-top: 20px;
        padding: 10px;
        border-top: 2px solid #ccc;
    }

    .cta {
        margin-top: 20px;
        text-align: center;
        margin-left: auto; 
        margin-right: 20px; 
    }

    .cta button {
        background: #ff9999;
        border: none;
        padding: 10px 20px;
        border-radius: 5px;
        cursor: pointer;
        margin-top: 10px;
    }

    .cta button:hover {
        background: #ffcccc;
    }
</style>

<div class="container">
    <h1>🚨 Water Contamination Alerts 🚨</h1>
    
    {#each alerts as alert (alert.id)}
        <div class="alert">
            <p>{alert.message}</p>
            <p><small>{alert.time}</small></p>
        </div>
    {/each}

    <div class="info-section">
        <h2>Why is this happening? 💧</h2>
        <p>Recent tests have shown increased levels of contamination in various locations.  
           It is advised to avoid direct contact with water in these areas until further notice.</p>
    </div>

    <div class="cta">
        ⚠️ Stay Safe! Report Any Issues ⚠️
        <br />
        <button on:click={() => alert("Thank you for staying informed!")}>Report a Problem</button>
    </div>
</div>
<script>
    let suggestions = [
        "Drink only purified or boiled water.",
        "Avoid ice cubes in drinks unless made from purified water.",
        "Wash your hands frequently with soap and clean water.",
        "Avoid eating raw or undercooked food.",
        "Keep your surroundings clean to prevent mosquito breeding.",
        "Use insect repellent to avoid mosquito bites.",
        "Dispose of waste properly to prevent contamination.",
        "Ensure proper sanitation and hygiene in your home."
    ];
</script>

<style>
    .suggestions {
        font-family: 'Arial', sans-serif;
        margin: 20px;
        padding: 20px;
        background-color: #f9f9f9;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        color: black;
    }
    .suggestions h2 {
        color: #2c3e50;
        text-align: center;
        margin-bottom: 20px;
    }
    .suggestions ul {
        list-style-type: disc;
        margin-left: 20px;
    }
    .suggestions li {
        margin-bottom: 10px;
        padding: 10px;
        background-color: #ffffff;
        border-radius: 5px;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        transition: transform 0.2s, box-shadow 0.2s;
    }
    .suggestions li:hover {
        transform: translateY(-2px);
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }
</style>

<div class="suggestions">
    <h2>💡 Health and Safety Suggestions 💡</h2>
    <ul>
        {#each suggestions as suggestion}
            <li>{suggestion}</li>
        {/each}
    </ul>
</div>
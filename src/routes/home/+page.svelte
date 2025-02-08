<script>
    // No JavaScript changes needed here!
</script>

<div class="container h-full mx-auto flex justify-center items-center">
    <div class="space-y-10 text-center flex flex-col items-center">
        <h2 class="text-3xl font-bold text-white">🚰 Welcome to HealthScope!</h2>
        <p class="text-lg text-white max-w-2xl">
            🌆 HealthScope helps you analyze water quality in urban areas, especially New York City 🗽.
            Simply enter a few values, and we'll provide insights and suggestions to improve water quality! 💦
        </p>

        <!-- Feature Boxes with Emojis and Images -->
        <div class="grid grid-cols-2 gap-6 p-6 bg-gray-100 rounded-lg shadow-lg w-full max-w-3xl">
            <!-- AI Analyzer Box -->
            <div class="bg-white p-6 rounded-lg shadow-md flex flex-col items-center">
                <img src="/image.png" alt="AI Analysis" class="w-16 h-16 mb-2">
                <h3 class="text-lg font-semibold text-black">🤖 Water Potability AI Analyzer</h3>
                <a href="/keyfeature1" class="mt-4 px-4 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600 transition">Analyze</a>
            </div>

            <!-- Community Outbreaks -->
            <div class="bg-white p-6 rounded-lg shadow-md flex flex-col items-center">
                <img src="/map.png" alt="Community Outbreaks" class="w-16 h-16 mb-2">
                <h3 class="text-lg font-semibold text-black">🌍 Community Outbreaks</h3>
                <a href="/keyfeature2" class="mt-4 px-4 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600 transition">Locate</a>
            </div>

            <!-- Alerts -->
            <div class="bg-white p-6 rounded-lg shadow-md flex flex-col items-center">
                <img src="/alerts.png" alt="Alerts" class="w-16 h-16 mb-2">
                <h3 class="text-lg font-semibold text-black">🚨 Alerts</h3>
                <a href="/keyfeature3" class="mt-4 px-4 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600 transition">Search</a>
            </div>

            <!-- Suggestions -->
            <div class="bg-white p-6 rounded-lg shadow-md flex flex-col items-center">
                <img src="/suggestions.png" alt="Suggestions" class="w-16 h-16 mb-2">
                <h3 class="text-lg font-semibold text-black">💡 Suggestions</h3>
                <a href="/keyfeature4" class="mt-4 px-4 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600 transition">Find</a>
            </div>
        </div>
    </div>
</div>

<style>
    .container {
        margin-left: 100px; /* Moves the entire section slightly to the right */
    }
    .grid {
        display: grid;
        gap: 1.5rem;
        background-color: #f3f4f6;
        border-radius: 0.5rem;
        box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
        width: 100%;
    }
    .bg-white {
        transition: transform 0.3s ease-in-out;
    }
    .bg-white:hover {
        transform: scale(1.05); /* Adds a hover effect */
    }
</style>

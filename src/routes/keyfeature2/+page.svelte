<script>
    import { onMount } from 'svelte';
    import L from 'leaflet';
    import 'leaflet/dist/leaflet.css';

    let map;

    onMount(() => {
        map = L.map('map').setView([40.7128, -74.0060], 10);

        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
        }).addTo(map);

        const locations = [
            { lat: 40.7128, lng: -74.0060 },
            { lat: 40.730610, lng: -73.935242 },
            { lat: 40.758896, lng: -73.985130 },
            { lat: 40.758880, lng: -73.985320 },
            { lat: 40.756789, lng: -73.985230 },
            { lat: 40.7290, lng: -73.985130 },
            { lat: 40.7290, lng: -73.976530 },
            { lat: 40.7000, lng: -73.976530 },
            { lat: 40.7290, lng: -73.986530 },
            { lat: 40.7290, lng: -73.999999 },
            { lat: 40.7290, lng: -73.888880 },
        ];

        locations.forEach(location => {
            L.marker([location.lat, location.lng], {
                icon: L.icon({
                    iconUrl: 'https://maps.google.com/mapfiles/ms/icons/red-dot.png',
                    iconSize: [32, 32],
                    iconAnchor: [16, 32]
                })
            }).addTo(map);
        });
    });
</script>

<style>
    #map {
        height: 100%;
        width: 100%;
    }
</style>

<div id="map"></div>
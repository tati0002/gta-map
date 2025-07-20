<!DOCTYPE html>
<html>
<head>
  <title>GTA 5 Interactive Map</title>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
  <style>
    html, body, #map {
      height: 100%;
      margin: 0;
    }
  </style>
</head>
<body>

<div id="map"></div>

<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
<script>
  // 1. กำหนดขนาดของภาพแผนที่ (ตามขนาดจริงของภาพที่ใช้)
  const mapWidth = 5000;  // ตัวอย่าง
  const mapHeight = 5000;

  const map = L.map('map', {
    crs: L.CRS.Simple,
    minZoom: -2,
    maxZoom: 2,
    zoomSnap: 0.25,
  });

  const bounds = [[0,0], [mapHeight, mapWidth]];

  // 2. โหลดแผนที่จากภาพ
  const image = L.imageOverlay('https://static.gta-5-map.com/images/fullmap/map.jpg', bounds).addTo(map);
  map.fitBounds(bounds);

  // 3. เพิ่ม marker ตำแหน่งสถานที่ (เช่น ปืน ร้าน)
  const gunIcon = L.icon({
    iconUrl: 'https://cdn-icons-png.flaticon.com/512/2922/2922013.png',
    iconSize: [32, 32],
    iconAnchor: [16, 32],
    popupAnchor: [0, -32]
  });

  const shopIcon = L.icon({
    iconUrl: 'https://cdn-icons-png.flaticon.com/512/3176/3176361.png',
    iconSize: [32, 32],
    iconAnchor: [16, 32],
    popupAnchor: [0, -32]
  });

  // ตัวอย่างตำแหน่ง (x, y) ในพิกัดภาพ
  L.marker([2500, 2000], { icon: gunIcon }).addTo(map).bindPopup("<b>Ammu-Nation</b><br>Gun Shop");
  L.marker([3000, 1800], { icon: shopIcon }).addTo(map).bindPopup("<b>Clothing Store</b><br>Urban Style");

</script>

</body>
</html>

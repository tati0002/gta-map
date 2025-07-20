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

 
</script>

</body>
</html>

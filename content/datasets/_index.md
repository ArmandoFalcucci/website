---
title: Datasets (attribute data and 3D models)
cms_exclude: true

# View.
#   1 = List
#   2 = Compact
#   3 = Card
view: 2

# Add this block to disable the page animation
design:
  animation: "none"

# Optional header image (relative to `static/media/` folder).
header:
  caption: ''
  image: ''

---

<style>
  #dataset-map {
    width: 100%;
    max-width: 1200px; /* scale down if needed */
    height: 750px;     /* adjust proportionally: 2064/3311 * 1200 ≈ 750 */
    margin-bottom: 2em;
  }
  .popup-thumb {
    width: 120px;
    height: auto;
    display: block;
    margin-bottom: 0.5em;
    border-radius: 6px;
  }
  .popup-links a {
    display: block;
    text-decoration: underline;
    margin: 0.15em 0;
  }
</style>

<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />

<div id="dataset-map"></div>

<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
<script>
(function() {
  const imageWidth = 3311;
  const imageHeight = 2064;

  // Initialize map with CRS.Simple
  const map = L.map('dataset-map', {
    crs: L.CRS.Simple,
    minZoom: -1,
    maxZoom: 2
  });

  // Full image bounds
  const bounds = [[0, 0], [imageHeight, imageWidth]];

  // Add static image overlay
  L.imageOverlay('/media/map-dataset.png', bounds).addTo(map);

  // Zoom in on Mediterranean region by defining subset of image bounds
  const medBounds = [[400, 1300], [1000, 2800]]; // y1,x1 -> y2,x2
  map.fitBounds(medBounds);

  // Build popup HTML
  function buildPopup(site) {
    let html = '';
    if (site.thumbnail) {
      html += `<img class="popup-thumb" src="${site.thumbnail}" alt="Thumbnail for ${site.name}">`;
    }
    html += `<strong>${site.name}</strong><br>`;
    html += '<div class="popup-links">';
    if (site.attribute_url) html += `<a href="${site.attribute_url}" target="_blank">Attribute data</a>`;
    if (site["3d_url"]) html += `<a href="${site["3d_url"]}" target="_blank">3D data</a>`;
    html += '</div>';
    return html;
  }

  // Load JSON and add markers
  fetch('/data/datasets.json', { cache: 'no-cache' })
    .then(r => r.json())
    .then(data => {
      data.forEach(site => {
        // Use pixel coordinates directly
        L.marker([site.y, site.x]).addTo(map).bindPopup(buildPopup(site));
      });
    })
    .catch(err => console.error('Error loading datasets.json:', err));

})();
</script>




Over the years, I have published a number of lithic datasets from important sites across the Mediterranean. This interactive map allows you to locate the sites and access the corresponding repositories:

- **Attribute data:** Detailed datasets containing continuous, ordinal, and categorical data of lithic artifacts with related contextual information.

- **3D data:** High-resolution 3D scans of selected stone tools, mostly cores, retouched tools, and laminar blanks. These repositories are part of the **[Open Aurignacian Project](https://www.armandofalcucci.com/project/open_aurignacian/)**.

Click on a site marker to open a popup with links to both the **attribute dataset** and the **3D models**.  

**Note:** The code is not behaving as expected and the pins are not on the exact location until you zoom in. I am working to solve this issue.

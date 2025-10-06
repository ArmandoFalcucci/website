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

<div id="dataset-map"></div>

<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
<script>
(function() {
  const imageWidth = 3311;
  const imageHeight = 2064;

  const map = L.map('dataset-map', {
    crs: L.CRS.Simple,
    minZoom: -1,
    maxZoom: 2,
    zoomControl: true
  });

  const bounds = [[0,0], [imageHeight, imageWidth]];

  // Add the static image
  L.imageOverlay('/media/map-dataset.png', bounds).addTo(map);

  // Set the map view zoomed in to fill the container
  // Center at middle of image
  const centerY = imageHeight / 2;
  const centerX = imageWidth / 2;

  // Set initial zoom level (adjust 0-2 depending on how much you want to zoom)
  map.setView([centerY, centerX], 1.2);

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

  fetch('/data/datasets.json', { cache: 'no-cache' })
    .then(r => r.json())
    .then(data => {
      data.forEach(site => {
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

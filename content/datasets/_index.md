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

<div style="position: relative; display: inline-block;">
  <img src="/media/map-dataset.png" width="3311" height="2064" alt="Map of sites">

  <!-- Grotta di Fumane -->
  <div class="site-pin"
       style="position: absolute; left: 1184px; top: 734px; transform: translate(-50%, -50%);
              width: 30px; height: 30px; background: red; border-radius: 50%; cursor: pointer; z-index:1000;"
       data-name="Grotta di Fumane"
       data-thumbnail="/media/fumane.jpg"
       data-attribute="https://zenodo.org/doi/10.5281/zenodo.10965413"
       data-3d="https://zenodo.org/doi/10.5281/zenodo.6362149">
  </div>

  <!-- Riparo Bombrini -->
  <div class="site-pin"
       style="position: absolute; left: 1008px; top: 872px; transform: translate(-50%, -50%);
              width: 30px; height: 30px; background: blue; border-radius: 50%; cursor: pointer; z-index:1000;"
       data-name="Riparo Bombrini"
       data-thumbnail="/media/bombrini.jpg"
       data-attribute="https://zenodo.org/doi/10.5281/zenodo.15363594"
       data-3d="https://zenodo.org/doi/10.5281/zenodo.14731694">
  </div>

  <!-- Grotta di Castelcivita -->
  <div class="site-pin"
       style="position: absolute; left: 1430px; top: 1115px; transform: translate(-50%, -50%);
              width: 30px; height: 30px; background: green; border-radius: 50%; cursor: pointer; z-index:1000;"
       data-name="Grotta di Castelcivita"
       data-thumbnail="/media/castelcivita.jpg"
       data-attribute="https://doi.org/10.5281/zenodo.10639552"
       data-3d="https://doi.org/10.5281/zenodo.10631389">
  </div>

  <!-- Grotta della Cala -->
  <div class="site-pin"
       style="position: absolute; left: 1420px; top: 1146px; transform: translate(-50%, -50%);
              width: 30px; height: 30px; background: orange; border-radius: 50%; cursor: pointer; z-index:1000;"
       data-name="Grotta della Cala"
       data-thumbnail="/media/cala.jpg"
       data-attribute="https://zenodo.org/doi/10.5281/zenodo.15430432"
       data-3d="https://zenodo.org/doi/10.5281/zenodo.14165189">
  </div>

  <!-- Ksar Akil -->
  <div class="site-pin"
       style="position: absolute; left: 2525px; top: 1458px; transform: translate(-50%, -50%);
              width: 30px; height: 30px; background: purple; border-radius: 50%; cursor: pointer; z-index:1000;"
       data-name="Ksar Akil"
       data-thumbnail="/media/ksarAkil.jpg"
       data-attribute="https://zenodo.org/doi/10.5281/zenodo.16932273"
       data-3d="">
  </div>
</div>

<!-- Popup container -->
<div id="popup" style="position:absolute; display:none; background:white; border:1px solid #333; padding:10px; border-radius:6px; z-index:2000;"></div>

<script>
  const popup = document.getElementById('popup');
  const pins = document.querySelectorAll('.site-pin');

  pins.forEach(pin => {
    pin.addEventListener('click', function(e){
      const rect = e.target.getBoundingClientRect();
      const bodyRect = document.body.getBoundingClientRect();
      popup.style.left = (rect.left - bodyRect.left + rect.width/2) + 'px';
      popup.style.top = (rect.top - bodyRect.top - 10) + 'px';
      
      let html = '';
      if(this.dataset.thumbnail) {
        html += `<img src="${this.dataset.thumbnail}" width="120" style="display:block;margin-bottom:5px">`;
      }
      html += `<strong>${this.dataset.name}</strong><br>`;
      if(this.dataset.attribute) html += `<a href="${this.dataset.attribute}" target="_blank">Attribute data</a>`;
      if(this.dataset['3d']) html += `<a href="${this.dataset['3d']}" target="_blank">3D data</a>`;
      
      popup.innerHTML = html;
      popup.style.display = 'block';
    });
  });

  // Hide popup when clicking anywhere else
  document.addEventListener('click', function(e){
    if(!e.target.classList.contains('site-pin')) {
      popup.style.display = 'none';
    }
  });
</script>


Over the years, I have published a number of lithic datasets from important sites across the Mediterranean. This interactive map allows you to locate the sites and access the corresponding repositories:

- **Attribute data:** Detailed datasets containing continuous, ordinal, and categorical data of lithic artifacts with related contextual information.

- **3D data:** High-resolution 3D scans of selected stone tools, mostly cores, retouched tools, and laminar blanks. These repositories are part of the **[Open Aurignacian Project](https://www.armandofalcucci.com/project/open_aurignacian/)**.

Click on a site marker to open a popup with links to both the **attribute dataset** and the **3D models**.  

**Note:** The code is not behaving as expected and the pins are not on the exact location until you zoom in. I am working to solve this issue.

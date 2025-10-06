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
  <div style="
    width: 24px;
    height: 24px;
    background: red;
    border-radius: 50%;
    position: absolute;
    left: 1184px;
    top: 734px;
    transform: translate(-50%, -50%);
    cursor: pointer;"
    title="Grotta di Fumane"
    onclick="window.open('https://zenodo.org/doi/10.5281/zenodo.10965413', '_blank')">
  </div>

  <!-- Riparo Bombrini -->
  <div style="
    width: 24px;
    height: 24px;
    background: blue;
    border-radius: 50%;
    position: absolute;
    left: 1008px;
    top: 872px;
    transform: translate(-50%, -50%);
    cursor: pointer;"
    title="Riparo Bombrini"
    onclick="window.open('https://zenodo.org/doi/10.5281/zenodo.15363594', '_blank')">
  </div>

  <!-- Grotta di Castelcivita -->
  <div style="
    width: 24px;
    height: 24px;
    background: green;
    border-radius: 50%;
    position: absolute;
    left: 1430px;
    top: 1115px;
    transform: translate(-50%, -50%);
    cursor: pointer;"
    title="Grotta di Castelcivita"
    onclick="window.open('https://doi.org/10.5281/zenodo.10639552', '_blank')">
  </div>

  <!-- Grotta della Cala -->
  <div style="
    width: 24px;
    height: 24px;
    background: orange;
    border-radius: 50%;
    position: absolute;
    left: 1420px;
    top: 1146px;
    transform: translate(-50%, -50%);
    cursor: pointer;"
    title="Grotta della Cala"
    onclick="window.open('https://zenodo.org/doi/10.5281/zenodo.15430432', '_blank')">
  </div>

  <!-- Ksar Akil -->
  <div style="
    width: 24px;
    height: 24px;
    background: purple;
    border-radius: 50%;
    position: absolute;
    left: 2525px;
    top: 1458px;
    transform: translate(-50%, -50%);
    cursor: pointer;"
    title="Ksar Akil"
    onclick="window.open('https://zenodo.org/doi/10.5281/zenodo.16932273', '_blank')">
  </div>

</div>




Over the years, I have published a number of lithic datasets from important sites across the Mediterranean. This interactive map allows you to locate the sites and access the corresponding repositories:

- **Attribute data:** Detailed datasets containing continuous, ordinal, and categorical data of lithic artifacts with related contextual information.

- **3D data:** High-resolution 3D scans of selected stone tools, mostly cores, retouched tools, and laminar blanks. These repositories are part of the **[Open Aurignacian Project](https://www.armandofalcucci.com/project/open_aurignacian/)**.

Click on a site marker to open a popup with links to both the **attribute dataset** and the **3D models**.  

**Note:** The code is not behaving as expected and the pins are not on the exact location until you zoom in. I am working to solve this issue.

FILES FOR THE WEBSITE
Folders: all_land, natural_vegetation.
    <folder>/YYYY.tif            burned area of that year (MCD64A1), one file per year 2001-2025
    <folder>/burn_probability.tif  percent of years with burned area (0-100, 255 = outside India or masked)
    <folder>/years_burned.tif      number of years with burned area (255 = outside India or masked)
    manifest.json                 bounds, size and file patterns for the web page (ba_viewer.html)
    india_states.geojson          simplified state outlines for the web page
    india_outline.geojson         India outer border (no internal lines) for the web page
    india_states_detail.geojson   finer state shapes for the page base map
    landcover.png                 land cover base map (MCD12Q1 2001 groups) for the page
    state_stats.json              per state burned area per year and area by years burned (web page statistics)
    <folder>/png/YYYY.png, probability.png, mfri.png   small preview images the page shows instantly

Format: single band GeoTIFF, EPSG:4326 (WGS84), 500 m (0.00417 deg), tiled, deflate compressed, with internal
overviews (average, nodata ignored; the full resolution band keeps the exact values). Pixel values are real data values so a hover read out shows them:
    YYYY.tif : day of year of burning (1-366); 0 = not burned (nodata)
Day of year to date: date = 1 January + (value - 1) days of that year.
Folder meaning: all_land = every land cover inside the India shapefile (no MODIS land cover mask); natural_vegetation = only MCD12Q1 2001 natural vegetation (IGBP 1-10), cropland and others removed.

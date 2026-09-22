# Όλα 1,40 storefront

A mobile-friendly product catalogue and wishlist storefront. Products are loaded at runtime from `Products.csv`, so adding or editing rows in that file updates the catalogue after the page is refreshed.

## Add the official logo

The repository currently references `assets/logo.png`. Add the original store logo image there without changing it. Until then, the header displays a text fallback.

## Product updates

Edit `Products.csv` and commit the changes to GitHub. The website fetches the CSV on each load with a cache-busting query, so visitors will see the updated product list after refreshing. For automatic updates from Google Sheets, publish the sheet as CSV and replace `CSV_URL` near the top of `app.js` with the published CSV URL.

Supported columns include `ID`, `Name`, `Name_gr`, `Category`, `Subcategory`, `Image_url`, `In stock`, `Variation`, and `Dimension`.

## Run locally

Use a local web server because browsers block `fetch()` from opening a local CSV directly:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

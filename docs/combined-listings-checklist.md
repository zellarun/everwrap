# EverWrap — Combined Listings Setup Checklist

Goal: one product page per product line (EverBox, EverEnvelope, EverBag, Accessories, Charms) that shows every option, while the collection pages keep showing each individual product.

**Rules for this project**
- Nothing is deleted, archived or redirected.
- The 8 bundles are not edited.
- Every parent listing is set to **Unlisted** (hidden from collections/search, reachable by URL).
- Collection cards keep linking to each product's own page.
- Shopify admin labels may differ slightly from what's written here.

---

## Step 0 — Before you start

- [ ] **Install the Combined Listings app** (by Shopify) from the Shopify App Store. It's free on Plus.
- [ ] **Theme:** the product page needs the Variant picker block, or the options won't show. This is ready on the git branch `feature/combined-listings-pdp` but **is not live yet**. Coordinate with the developer to get it live before (or at the same moment as) the first listing.
- [ ] **Confirm SKUs:** check that no warehouse, 3PL, Amazon or other sales channel uses the EverBow SKU `20COZTRI-BMST-1`.
- [ ] **Bundle baseline:** for each of the 8 bundles below, write down its components (Apps → Shopify Bundles) and check on the live store that it adds to cart and reaches the checkout payment page. Don't pay. Take screenshots.
  - Large Bundle – Sampler Pack in Red, Blue, and White
  - Large Bundle – Sampler Pack in Pink, Gold, and Black
  - Small Bundle (Pink, Gold, and Black)
  - Small Bundle (Red and Blue)
  - Medium Bundle (Red and Blue)
  - Medium Bundle (Pink, Gold, and Black)
  - Medium Bundle (Green and Pink)
  - Small Bundle – 9 piece starter set *(unpublished)*

---

## Step 1 — Data fixes

- [ ] **EverBow SKUs** (Products → open each → Variant SKU):

  | Product | Old SKU | New SKU |
  |---|---|---|
  | EverBow: Black | 20COZTRI-BMST-1 | 20COZTRI-BMST-BLK |
  | EverBow: Navy | 20COZTRI-BMST-1 | 20COZTRI-BMST-NVY |
  | EverBow: Pink | 20COZTRI-BMST-1 | 20COZTRI-BMST-PNK |
  | EverBow: Red | 20COZTRI-BMST-1 | 20COZTRI-BMST-RED |

- [ ] **Tag typo:** on "EverBox: Small Red + White Collapsible Gift Box…" (`everbox-cabin-mini`), remove the tag `Cabin Colection` and add `Cabin Collection`.

---

## Step 2 — Pilot: EverBox

Apps → Combined Listings → **Create combined listing**

- [ ] Title: **EverBox**
- [ ] Add these 8 products:

  | Product (title starts with) | Handle | Collection | Size |
  |---|---|---|---|
  | EverBox: Small Red + White… | everbox-cabin-mini | Cabin | Small |
  | EverBox: Medium Navy Blue… | everbox-cabin-small | Cabin | Medium |
  | EverBox: Large Blue Plaid… | everbox-cabin-medium | Cabin | Large |
  | EverBox: Extra Large Red… | everbox-cabin-large | Cabin | XL |
  | EverBox: Small Black, White and Pink… | copy-of-everbox-cozy-mini | Cozy | Small |
  | EverBox: Medium Pink… | everbox-cozy-small | Cozy | Medium |
  | EverBox: Large Pink Plaid… | everbox-cozy-medium | Cozy | Large |
  | EverBox: Extra Large Yellow… | everbox-large | Cozy | XL |

- [ ] Options: **Collection** (first), **Size** (second). Enter the values exactly as in the table. Size order: Small, Medium, Large, XL.
- [ ] Save. It saves as Draft.
- [ ] Open the new **EverBox** parent in Products:
  - Status → **Unlisted**
  - Sales channels → Online Store is on
  - Search engine listing → URL handle is `everbox`

---

## Step 3 — Test the EverBox pilot

Use the live store on desktop **and** a phone.

**Collection page**
- [ ] All 8 EverBox cards still show.
- [ ] There is **no** extra "EverBox" parent card.

**Product page**
- [ ] Click the Cabin Small card. Collection and Size buttons show, with Cabin + Small selected.
- [ ] Click **Cozy**. Photos, title, price and URL change to the Cozy Small box.
- [ ] Click **XL**. Price changes to $19.99.
- [ ] The low-stock message updates when switching.
- [ ] Add to cart. The cart shows the right box.
- [ ] `/products/everbox` opens and shows the buttons.

**Filters and search**
- [ ] On the EverBox collection page, try each filter. **Write down whether any cards disappear.**
- [ ] Search "everbox". Write down what shows up.

**Bundles (critical)**
- [ ] Repeat the Step 0 bundle check for all 8 bundles: components unchanged in the Bundles app, adds to cart, reaches the payment page.
- [ ] **If any bundle is broken:** Apps → Combined Listings → EverBox → remove the products from the listing (or delete the listing). The individual products stay. Before confirming, check that Shopify's prompt says the products are kept. Then re-check the bundle.

**Report back** before continuing: filter results, search results, bundle results and any screenshots. The filter decision gets made at this point.

---

## Step 4 — Roll out the rest (only after the pilot is signed off)

For each listing, repeat Step 2 (create → Unlisted → check the URL handle) and Step 3 (test, including bundles).

### EverEnvelope — `/products/everenvelope`
Options: **Collection**, **Size** (Small, Medium, Large)

| Product (title starts with) | Handle | Collection | Size |
|---|---|---|---|
| EverEnvelope: Small Blue and Red Print… | evergift-cabin-small | Cabin | Small |
| EverEnvelope: Medium Red and White… | evergift-cabin-medium | Cabin | Medium |
| EverEnvelope: Large Navy… Forest Animals… | evergift-cabin-large | Cabin | Large |
| EverEnvelope: Small Black and White… | evergift-cozy-small | Cozy | Small |
| EverEnvelope: Medium Black, White, & Marigold… | copy-of-evergift-cozy-medium | Cozy | Medium |
| EverEnvelope: Large Pink… | evergift-cozy-large | Cozy | Large |

### EverBag — `/products/everbag`
Options: **Collection** (Cabin, Cozy, Green), **Size** (Small, Medium, Large)

| Product (title starts with) | Handle | Collection | Size |
|---|---|---|---|
| EverBag: Small Leaf Design… *(leave unpublished)* | everbag-cabin-small | Cabin | Small |
| EverBag: Medium Holiday Red… Knitted Sweater… | everbag-cabin-medium | Cabin | Medium |
| EverTie: Large Blue Tie Bag… | everbag-large-cotton-blue-tie-bag-with-satin-ribbon-closure | Cabin | Large |
| EverBag: Small Grey and Gold Floral… | everbag-cozy-small | Cozy | Small |
| EverBag: Medium Black and White Buffalo Check… | everbag-cozy-medium | Cozy | Medium |
| EverTie: Large Tie Bag with Black Grid… | everbag-large-cotton-black-grid-tie-bag-with-satin-ribbon-closure | Cozy | Large |
| EverBag: Small Green Floral Print… | everbag-small-green-floral-print-with-ivory-satin-bow | Green | Small |
| EverBag: Medium Green Buffalo Plaid… | everbag-medium-green-buffalo-plaid-with-ivory-satin-bow-copy | Green | Medium |

Expected: Cabin × Small shows as unavailable (the product is unpublished), and Green × Large shows as unavailable (it doesn't exist).

### Accessories — `/products/accessories`
Options: **Item**, **Color** (Color linked to the Color metafield so swatches show)

First, set the **Color** category metafield on each product (Products → open → Category metafields → Color):

| Product | Handle | Color metafield |
|---|---|---|
| EverBow: Black | everbow | Black |
| EverBow: Navy | everbow-navy | Navy |
| EverBow: Pink | everbow-pink | Pink |
| EverBow: Red | everbow-red | Red |
| Gift Tags (10 Pack) | gift-tags | **Kraft** (new custom color entry with a kraft-brown swatch) |

Then create the listing:

| Product | Item | Color |
|---|---|---|
| EverBow: Black | EverBow | Black |
| EverBow: Navy | EverBow | Navy |
| EverBow: Pink | EverBow | Pink |
| EverBow: Red | EverBow | Red |
| Gift Tags (10 Pack) | Gift Tags | Kraft |

- [ ] When adding the **Color** option, choose to connect it to the **Color** category metafield instead of typing the values.
- [ ] Test: color circles show on the product page.

### Charms — `/products/charms`
Option: **Design**

| Product | Handle | Design |
|---|---|---|
| Charm: Wooden tag with gold heart | charms-wooden-tag-with-gold-heart | Gold Heart |
| Charm: Snowflake | charm-wooden-tag-with-gold-heart-copy | Snowflake |
| Charm: Star | charm-wooden-snowflake-copy | Star |
| Charm: Tree | charm-tree | Tree |

---

## Not included
- The 8 bundles (see Step 0)
- Related products section on the product page (unchanged)
- Collection page filters (decided after the pilot)

## Known Shopify limitations
- Child products of a combined listing are left out of Search & Discovery **filter** results.
- A combined listing can't be a bundle, be added to a bundle, or be used as a Featured product. The homepage featured product is a bundle, so it isn't affected.
- Sibling products may show up in each other's "Related products".

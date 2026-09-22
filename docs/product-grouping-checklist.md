# EverWrap — Product Grouping Setup Checklist (no app)

Product titles below are the new SEO titles (see `docs/seo-copy-review.md`). Handles never change, so you can also search by handle.

Goal: one product page experience per product line (EverBox, EverEnvelope, EverBag, EverTie, Accessories, Charms), Amazon-style. On any product in a line, shoppers see **photo swatches** for every pattern in that line and, where the line has sizes, **size pills with dimensions**. A pattern or size that isn't in stock together is blacked out. Collection pages keep showing each product as its own card.

How it works: the theme reads two new fields on each product (its pattern and size, e.g. **Buffalo Check** / **Medium**) plus one "Product group" entry per line that lists the products and the button order. No app, and no product is rebuilt, deleted or redirected.

**Rules for this project**
- Don't delete, archive, redirect or add variants to any product.
- Don't edit the 8 starter sets (Shopify Bundles).
- Type values exactly as written. Spelling, capitals and spaces must match between the product fields and the group entry.
- Each product can be in **one** group only.
- Shopify admin labels may differ slightly from what's written here.

---

## Step 1 — Create the fields (one time)

### 1a. Two product fields
Settings → Custom data → **Products** → Add definition. Create both:

| Name | Namespace and key | Type |
|---|---|---|
| Group option 1 | `custom.group_option_1` | Single line text, one value |
| Group option 2 | `custom.group_option_2` | Single line text, one value |

### 1b. The "Product group" entry type
Settings → Custom data → **Metaobjects** → Add definition

- Name: **Product group**
- Type: **`product_group`**. The theme also accepts `product` or `products`, so an existing definition with one of those types works too.
- Fields (check that each **key** matches):

  | Field name | Key | Type |
  |---|---|---|
  | Name | `name` | Single line text (set as the display name) |
  | Option 1 name | `option_1_name` | Single line text |
  | Option 1 values | `option_1_values` | Single line text, **List of values** |
  | Option 2 name | `option_2_name` | Single line text |
  | Option 2 values | `option_2_values` | Single line text, **List of values** |
  | Option 2 details | `option_2_details` | Single line text, **List of values** (the dimensions shown under each size pill, same order as Option 2 values) |
  | Products | `products` | Product, **List of values** |
  | Videos | `videos` | File (videos only), **List of values** |

- Access: turn **Storefronts** access **on**. The theme can't see the groups without it.
- If there's an "Active / Draft status" option, entries must be set to **Active**.

---

## Step 2 — Data fixes

- [ ] Give each EverBow its own SKU (first confirm no warehouse, 3PL or Amazon listing uses `20COZTRI-BMST-1`):

  | Product | Old SKU | New SKU |
  |---|---|---|
  | EverBow Reusable Gift Bow – Black | 20COZTRI-BMST-1 | 20COZTRI-BMST-BLK |
  | EverBow Reusable Gift Bow – Navy | 20COZTRI-BMST-1 | 20COZTRI-BMST-NVY |
  | EverBow Reusable Gift Bow – Pink | 20COZTRI-BMST-1 | 20COZTRI-BMST-PNK |
  | EverBow Reusable Gift Bow – Red | 20COZTRI-BMST-1 | 20COZTRI-BMST-RED |

- [ ] On "EverBox Collapsible Gift Box – Red & White, Small" (`everbox-cabin-mini`), change the tag `Cabin Colection` to `Cabin Collection`.

---

## Step 3 — Pattern and size on each product

**Fastest: import `docs/product-group-import.csv`.** It fills Group option 1 and 2 for all 31 products below. **Do Step 1 first**, because Shopify ignores values for fields that don't exist yet.
Products → Import → choose the file → tick **Overwrite products with matching handles** → Upload and preview (31 products, all updates, none new) → Import products.

It only changes these two fields. The title and option columns hold the current values because Shopify's importer requires them.

The tables below show what the file contains. You can also type the values in the bulk editor instead.

### EverBox
| Product | Handle | Group option 1 (pattern) | Group option 2 (size) |
|---|---|---|---|
| EverBox Collapsible Gift Box – Red & White, Small | everbox-cabin-mini | Red & White | Small |
| EverBox Collapsible Gift Box – Black, White & Pink, Small | copy-of-everbox-cozy-mini | Black, White & Pink | Small |
| EverBox Collapsible Gift Box – Navy, Medium | everbox-cabin-small | Navy | Medium |
| EverBox Collapsible Gift Box – Pink, Medium | everbox-cozy-small | Pink | Medium |
| EverBox Collapsible Gift Box – Blue Plaid, Large | everbox-cabin-medium | Blue Plaid | Large |
| EverBox Collapsible Gift Box – Pink Plaid, Large | everbox-cozy-medium | Pink Plaid | Large |
| EverBox Collapsible Gift Box – Red, XL | everbox-cabin-large | Red | XL |
| EverBox Collapsible Gift Box – Yellow, XL | everbox-large | Yellow | XL |

### EverEnvelope
| Product | Handle | Group option 1 (pattern) | Group option 2 (size) |
|---|---|---|---|
| EverEnvelope Reusable Gift Bag – Blue & Red Print, Small | evergift-cabin-small | Blue & Red Print | Small |
| EverEnvelope Reusable Gift Bag – Black & White, Small | evergift-cozy-small | Black & White | Small |
| EverEnvelope Reusable Gift Bag – Red & White, Medium | evergift-cabin-medium | Red & White | Medium |
| EverEnvelope Reusable Gift Bag – Black, White & Marigold, Medium | copy-of-evergift-cozy-medium | Black, White & Marigold | Medium |
| EverEnvelope Reusable Gift Bag – Navy Forest Animals, Large | evergift-cabin-large | Navy Forest Animals | Large |
| EverEnvelope Reusable Gift Bag – Pink, Large | evergift-cozy-large | Pink | Large |

### EverBag
| Product | Handle | Group option 1 (pattern) | Group option 2 (size) |
|---|---|---|---|
| EverBag Reusable Gift Bag – Blue Berry Foliage, Small | everbag-cabin-small | Blue Berry Foliage | Small |
| EverBag Reusable Gift Bag – Grey & Gold Floral, Small | everbag-cozy-small | Grey & Gold Floral | Small |
| EverBag Reusable Gift Bag – Green Floral, Small | everbag-small-green-floral-print-with-ivory-satin-bow | Green Floral | Small |
| EverBag Reusable Gift Bag – Red Knit Sweater, Medium | everbag-cabin-medium | Red Knit Sweater | Medium |
| EverBag Reusable Gift Bag – Buffalo Check, Medium | everbag-cozy-medium | Buffalo Check | Medium |
| EverBag Reusable Gift Bag – Green Buffalo Plaid, Medium | everbag-medium-green-buffalo-plaid-with-ivory-satin-bow-copy | Green Buffalo Plaid | Medium |

EverBag no longer includes a "Large" size — the two EverTie products below moved into their own group, since a bow-tie bag isn't really a "Large" version of the other EverBags.

### EverTie (one row of swatches; leave Group option 2 empty)
| Product | Handle | Group option 1 |
|---|---|---|
| EverTie Tie Gift Bag – Blue, Large | everbag-large-cotton-blue-tie-bag-with-satin-ribbon-closure | Blue |
| EverTie Tie Gift Bag – Black Grid, Large | everbag-large-cotton-black-grid-tie-bag-with-satin-ribbon-closure | Black Grid |

These two already have Group option 1 set from the CSV import (Blue / Black Grid). Their Group option 2 field can stay as "Large" or be cleared — it's ignored once the EverTie group entry below has no Option 2 name.

### Accessories (one row of swatches; leave Group option 2 empty)
| Product | Handle | Group option 1 |
|---|---|---|
| EverBow Reusable Gift Bow – Black | everbow | Black Bow |
| EverBow Reusable Gift Bow – Navy | everbow-navy | Navy Bow |
| EverBow Reusable Gift Bow – Pink | everbow-pink | Pink Bow |
| EverBow Reusable Gift Bow – Red | everbow-red | Red Bow |
| Recycled Paper Gift Tags – 10 Pack | gift-tags | Gift Tags |

### Charms (one row of swatches; leave Group option 2 empty)
| Product | Handle | Group option 1 |
|---|---|---|
| Wooden Gold Heart Gift Charm | charms-wooden-tag-with-gold-heart | Gold Heart |
| Wooden Snowflake Gift Charm | charm-wooden-tag-with-gold-heart-copy | Snowflake |
| Alloy Star Gift Charm | charm-wooden-snowflake-copy | Star |
| Alloy Tree Gift Charm | charm-tree | Tree |

---

## Step 4 — Swatch photos

Each swatch is the product's **main photo** (its first image). No color fields are needed for the swatches. Check that each product's first photo is a clear, centered shot of the product.

The Color and Size category fields are still worth filling in for Google Shopping (see Part 3 of `docs/seo-copy-review.md`). They don't affect the swatches.

---

## Step 5 — Create the 6 Product group entries

Settings → Custom data → Metaobjects → **Product group** → Add entry. Each `·` below is a separate entry in the list. The order sets the order of the swatches and pills.

**EverBox**
- Option 1 name: **Color**. Values: Red & White · Black, White & Pink · Navy · Pink · Blue Plaid · Pink Plaid · Red · Yellow
- Option 2 name: **Size**. Values: Small · Medium · Large · XL
- Option 2 details: 8" x 8" x 8" · 12" x 8" x 8" · 16" x 12" x 8" · 16" x 12" x 12"
- Products: the 8 EverBox products above

**EverEnvelope**
- Option 1 name: **Color**. Values: Blue & Red Print · Black & White · Red & White · Black, White & Marigold · Navy Forest Animals · Pink
- Option 2 name: **Size**. Values: Small · Medium · Large
- Option 2 details: 9.5" x 7.5" x 4.5" · 13" x 10.5" x 6.25" · 16.25" x 13.5" x 6.5"
- Products: the 6 EverEnvelope products above

**EverBag**
- Option 1 name: **Color**. Values: Blue Berry Foliage · Grey & Gold Floral · Green Floral · Red Knit Sweater · Buffalo Check · Green Buffalo Plaid
- Option 2 name: **Size**. Values: Small · Medium
- Option 2 details: 8" x 8" x 4.5" · 11.5" x 9" x 7"
- Products: the 6 EverBag products above (**not** the 2 EverTie products — if they're still listed here from the earlier setup, remove them)

**EverTie**
- Option 1 name: **Color**. Values: Blue · Black Grid
- Option 2 name, values and details: leave empty
- Products: the 2 EverTie products above

**Accessories**
- Option 1 name: **Style**. Values: Black Bow · Navy Bow · Pink Bow · Red Bow · Gift Tags
- Option 2 name, values and details: leave empty
- Products: the 4 EverBows + Gift Tags

**Charms**
- Option 1 name: **Design**. Values: Gold Heart · Snowflake · Star · Tree
- Option 2 name, values and details: leave empty
- Products: the 4 charms

Nothing changes on the live store yet. The live theme doesn't read these fields until the new theme code is live (Step 6).

### 5b. Videos for a specific color/size (optional)

Videos show under the product photos, on desktop and phone. They change when a shopper switches options. If a product has no matching videos, nothing shows.

1. Open the line's Product group entry (e.g. EverBag) → **Videos** → upload or pick the videos.
2. Set each video's **alt text**: Content → **Files** → click the video → Alt text. The alt text says which products it belongs to.

A video shows on a product when its alt text contains **all** of that product's options (pattern **and** size). Capitals, commas and slashes don't matter.

| Alt text | Shows on |
|---|---|
| `Buffalo Check Medium` | the Buffalo Check EverBag |
| `Buffalo Check Green Buffalo Plaid Medium` | both Medium plaid EverBags |
| `Red XL` | the Red XL EverBox |
| `Pink Bow` | the Pink EverBow |
| `Snowflake` | the Snowflake charm |
| `All` | every product in that line |

- `Medium` on its own does **not** match anything. It also needs the pattern.
- Videos show in the order they're listed in the Videos field.
- Only videos uploaded to Shopify work here, not YouTube links.

### 5c. Reviews (Judge.me)

The product page now has a **"Loved by gift-givers"** reviews section above Related products, plus stars under the product title.

- **Stars and the summary** ("4.9 out of 5 · Based on 132 reviews of EverBox") add up the ratings of **every product in the line**. The numbers come from the ratings Judge.me syncs into Shopify, the same ones behind star ratings on product cards.
  - [ ] If the stars or summary don't appear, check in Judge.me that rating sync to Shopify is turned on and that the products have reviews.
- **Carousel:** the section includes the same Judge.me **Featured carousel** as the homepage. It shows reviews you mark as "featured" in Judge.me, from the whole store.
- **Optional, full review list with "Write a review":** Online Store → Themes → Customize → a product page → **Product reviews** section → Add block → **Judge.me Review Widget**.
  - ⚠️ This widget shows **one product's** reviews. The reviews section stays in place when shoppers switch options (so the carousel doesn't reload), so the widget would keep showing the first product's reviews. Only add it if Judge.me **Product groups** is set up to share reviews across each line. That's a Judge.me paid-plan feature.
- **Theme editor settings:** heading text and size, the summary on/off, and the card color. The default is the pink scheme used by Blog Posts.

---

## Step 6 — Preview the theme

The theme code is on git branch `feature/combined-listings-pdp`.
- [ ] Push the branch (developer).
- [ ] Online Store → Themes → Add theme → **Connect from GitHub** → pick `feature/combined-listings-pdp`. This adds an unpublished copy.
- [ ] Use **Preview** on that copy for all the tests in Step 7.

---

## Step 7 — Test on the preview theme (desktop **and** phone)

**Every group**
- [ ] The collection page still shows every product card, and filters and sorting still work.
- [ ] On a product page, the swatches and size pills show in the right order with the current product selected.
- [ ] Clicking another swatch or size swaps the photos, title, price, low-stock message and URL without a full reload.
- [ ] Add to cart adds the right product (check the cart).

**Specific checks**
- [ ] **Swatches:** every pattern in the line shows as a photo tile. The current product's tile has a dark border. No titles or prices show in the picker.
- [ ] **Size pills** show the dimensions under each size (e.g. "Medium · 11.5" x 9" x 7"").
- [ ] **Blacked-out sizes:** on the Buffalo Check EverBag (Medium), Small is blacked out (dark tile/pill, dashed border) since it isn't Medium.
- [ ] **Blacked-out patterns:** still on the Buffalo Check EverBag (Medium), any pattern swatch that doesn't come in Medium is also blacked out — not just the size pills.
- [ ] **EverTie:** EverTie shows as its own picker (Blue / Black Grid swatches only, no size pills), separate from EverBag.
- [ ] **EverBox:** clicking the Red swatch opens the Red XL box at $19.99, and the XL pill shows 16" x 12" x 12".
- [ ] **Accessories, Charms and EverTie:** one row of photo swatches and no size pills.
- [ ] **Unpublished products** (if any) don't show as swatches.
- [ ] **Sold out:** a sold-out pattern's swatch is blacked out, and its page shows "Sold out".
- [ ] **Videos:** give one EverBag video the alt text `Buffalo Check Medium`. It shows under the photos on that bag only, disappears when you switch to another pattern, and plays with sound when clicked. A product with no matching videos shows no video area.
- [ ] **Reviews:** stars and a number show under the title, and clicking them scrolls down to the "Loved by gift-givers" section. The summary count equals the total reviews across the whole line.
- [ ] **Reviews after switching:** switch options a few times. The Judge.me carousel stays visible, and its arrows still work.
- [ ] **Not affected:** bundles and any product not in a group look and work exactly as before. For a bundle, the stars and summary show that bundle's own rating.

**Report back** with anything that looks off, plus screenshots.

---

## Step 8 — Go live
- [ ] After sign-off, the developer merges the theme change into the live theme's branch. The groups work as soon as it's live.

---

## Also changed on the product page
- The **Variant picker** block was added, which is where the swatches and size pills render.
- The **Quick order list** section was removed.
- A **star rating** block was added under the title, and a **Product reviews** section was added above Related products.
- Related products is unchanged. Siblings may show there.

## Not included
- The 8 bundles
- Collection page layout and filters

## ⚠️ Keep the product template in git
Editing the **product page in the live theme's editor** makes Shopify rewrite `templates/product.json` on `main`. Merging `main` into this branch then replaces this branch's product template, which is what removed the picker, stars and reviews on Sep 18. Until this ships, avoid editing the product template in the live theme editor. If you merge `main` in again, check that `templates/product.json` still has the `variant_picker`, `rating` and `product_reviews` entries.

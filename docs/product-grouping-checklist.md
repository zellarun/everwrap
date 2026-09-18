# EverWrap — Product Grouping Setup Checklist (no app)

Product titles below are the new SEO titles (see `docs/seo-copy-review.md`). Handles never change, so you can also search by handle.

Goal: one product page experience per product line (EverBox, EverEnvelope, EverBag, Accessories, Charms). On any product in a line, shoppers see buttons for every option in that line and can switch between them. Collection pages keep showing each product as its own card.

How it works: the theme reads two new fields on each product (its option values, e.g. **Cabin** / **Small**) plus one "Product group" entry per line that lists the products and the button order. No app, and no product is rebuilt, deleted or redirected.

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
- Type: **`product_group`** (must be exactly this; the theme looks for it)
- Fields (check that each **key** matches):

  | Field name | Key | Type |
  |---|---|---|
  | Name | `name` | Single line text (set as the display name) |
  | Option 1 name | `option_1_name` | Single line text |
  | Option 1 values | `option_1_values` | Single line text, **List of values** |
  | Option 2 name | `option_2_name` | Single line text |
  | Option 2 values | `option_2_values` | Single line text, **List of values** |
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

## Step 3 — Sizes and options on each product

The fastest way is the bulk editor. Products → select the products → **Bulk edit** → Columns → add **Group option 1** and **Group option 2** → fill in from the tables below → Save.

### EverBox (Group option 1 = Collection, Group option 2 = Size)
| Product | Handle | Group option 1 | Group option 2 |
|---|---|---|---|
| EverBox Collapsible Gift Box – Red & White, Small | everbox-cabin-mini | Cabin | Small |
| EverBox Collapsible Gift Box – Navy, Medium | everbox-cabin-small | Cabin | Medium |
| EverBox Collapsible Gift Box – Blue Plaid, Large | everbox-cabin-medium | Cabin | Large |
| EverBox Collapsible Gift Box – Red, XL | everbox-cabin-large | Cabin | XL |
| EverBox Collapsible Gift Box – Black, White & Pink, Small | copy-of-everbox-cozy-mini | Cozy | Small |
| EverBox Collapsible Gift Box – Pink, Medium | everbox-cozy-small | Cozy | Medium |
| EverBox Collapsible Gift Box – Pink Plaid, Large | everbox-cozy-medium | Cozy | Large |
| EverBox Collapsible Gift Box – Yellow, XL | everbox-large | Cozy | XL |

### EverEnvelope (Collection, Size)
| Product | Handle | Group option 1 | Group option 2 |
|---|---|---|---|
| EverEnvelope Reusable Gift Bag – Blue & Red Print, Small | evergift-cabin-small | Cabin | Small |
| EverEnvelope Reusable Gift Bag – Red & White, Medium | evergift-cabin-medium | Cabin | Medium |
| EverEnvelope Reusable Gift Bag – Navy Forest Animals, Large | evergift-cabin-large | Cabin | Large |
| EverEnvelope Reusable Gift Bag – Black & White, Small | evergift-cozy-small | Cozy | Small |
| EverEnvelope Reusable Gift Bag – Black, White & Marigold, Medium | copy-of-evergift-cozy-medium | Cozy | Medium |
| EverEnvelope Reusable Gift Bag – Pink, Large | evergift-cozy-large | Cozy | Large |

### EverBag (Collection, Size)
| Product | Handle | Group option 1 | Group option 2 |
|---|---|---|---|
| EverBag Reusable Gift Bag – Blue Berry Foliage, Small *(stays unpublished)* | everbag-cabin-small | Cabin | Small |
| EverBag Reusable Gift Bag – Red Knit Sweater, Medium | everbag-cabin-medium | Cabin | Medium |
| EverTie Tie Gift Bag – Blue, Large | everbag-large-cotton-blue-tie-bag-with-satin-ribbon-closure | Cabin | Large |
| EverBag Reusable Gift Bag – Grey & Gold Floral, Small | everbag-cozy-small | Cozy | Small |
| EverBag Reusable Gift Bag – Buffalo Check, Medium | everbag-cozy-medium | Cozy | Medium |
| EverTie Tie Gift Bag – Black Grid, Large | everbag-large-cotton-black-grid-tie-bag-with-satin-ribbon-closure | Cozy | Large |
| EverBag Reusable Gift Bag – Green Floral, Small | everbag-small-green-floral-print-with-ivory-satin-bow | Green | Small |
| EverBag Reusable Gift Bag – Green Buffalo Plaid, Medium | everbag-medium-green-buffalo-plaid-with-ivory-satin-bow-copy | Green | Medium |

### Accessories (Item, Color)
| Product | Handle | Group option 1 | Group option 2 |
|---|---|---|---|
| EverBow Reusable Gift Bow – Black | everbow | EverBow | Black |
| EverBow Reusable Gift Bow – Navy | everbow-navy | EverBow | Navy |
| EverBow Reusable Gift Bow – Pink | everbow-pink | EverBow | Pink |
| EverBow Reusable Gift Bow – Red | everbow-red | EverBow | Red |
| Recycled Paper Gift Tags – 10 Pack | gift-tags | Gift Tags | Kraft |

### Charms (Design only; leave Group option 2 empty)
| Product | Handle | Group option 1 |
|---|---|---|
| Wooden Gold Heart Gift Charm | charms-wooden-tag-with-gold-heart | Gold Heart |
| Wooden Snowflake Gift Charm | charm-wooden-tag-with-gold-heart-copy | Snowflake |
| Alloy Star Gift Charm | charm-wooden-snowflake-copy | Star |
| Alloy Tree Gift Charm | charm-tree | Tree |

---

## Step 4 — Color swatches (Accessories only)

Only an option named **Color** shows color circles. Everything else shows as text buttons. The circle color comes from each product's **Color** category field.

Open each product → **Category metafields** → **Color**:

| Product | Color |
|---|---|
| EverBow Reusable Gift Bow – Black | Black |
| EverBow Reusable Gift Bow – Navy | Navy |
| EverBow Reusable Gift Bow – Pink | Pink |
| EverBow Reusable Gift Bow – Red | Red |
| Recycled Paper Gift Tags – 10 Pack | Add a new entry named **Kraft** with a kraft-brown color (e.g. `#C19A6B`) |

If a product has more than one color, the swatch uses the **first** one.

---

## Step 5 — Create the 5 Product group entries

Settings → Custom data → Metaobjects → **Product group** → Add entry. The order of the values sets the order of the buttons.

| Name | Option 1 name | Option 1 values (in order) | Option 2 name | Option 2 values (in order) | Products |
|---|---|---|---|---|---|
| EverBox | Collection | Cabin, Cozy | Size | Small, Medium, Large, XL | the 8 EverBox products above |
| EverEnvelope | Collection | Cabin, Cozy | Size | Small, Medium, Large | the 6 EverEnvelope products |
| EverBag | Collection | Cabin, Cozy, Green | Size | Small, Medium, Large | the 8 EverBag / EverTie products |
| Accessories | Item | EverBow, Gift Tags | Color | Black, Navy, Pink, Red, Kraft | the 4 EverBows + Gift Tags |
| Charms | Design | Gold Heart, Snowflake, Star, Tree | *(empty)* | *(empty)* | the 4 charms |

Nothing changes on the live store yet. The live theme doesn't read these fields until the new theme code is live (Step 6).

### 5b. Videos for a specific color/size (optional)

Videos show under the product photos, on desktop and phone. They change when a shopper switches options. If a product has no matching videos, nothing shows.

1. Open the line's Product group entry (e.g. EverBox) → **Videos** → upload or pick the videos.
2. Set each video's **alt text**: Content → **Files** → click the video → Alt text. The alt text says which products it belongs to.

A video shows on a product when its alt text contains **all** of that product's options. Capitals, commas and slashes don't matter.

| Alt text | Shows on |
|---|---|
| `Cozy Medium` | only the Cozy Medium product |
| `Cabin Cozy Medium` | both Cabin Medium and Cozy Medium |
| `Cabin Small Medium` | Cabin Small and Cabin Medium |
| `EverBow Pink` | the Pink EverBow |
| `Gift Tags Kraft` | Gift Tags |
| `Snowflake` | the Snowflake charm |
| `All` | every product in that line |

- `Medium` on its own does **not** show on EverBox products. It also needs the collection (Cabin/Cozy).
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
- [ ] On a product page, the buttons show in the right order with the current product selected.
- [ ] Clicking another button swaps the photos, title, price, low-stock message and URL without a full reload.
- [ ] Add to cart adds the right product (check the cart).

**Specific checks**
- [ ] **EverBox:** Cabin + XL shows the Extra Large Red box at $19.99.
- [ ] **EverBag:** Cabin + Small is crossed out because that product is unpublished. Clicking it opens Cozy Small.
- [ ] **EverBag:** on a Green bag, Large is crossed out. Clicking it opens a Large tie bag.
- [ ] **Accessories:** color circles show. Kraft is crossed out on a bow, and bow colors are crossed out on Gift Tags. Clicking one switches item.
- [ ] **Charms:** one row of Design buttons.
- [ ] **Sold out:** a sold-out product's button looks crossed out, and its page shows "Sold out".
- [ ] **Videos:** give one EverBox video the alt text `Cozy Medium`. It shows under the photos on Cozy Medium only, disappears when you switch to Cabin Medium, and plays with sound when clicked. A product with no matching videos shows no video area.
- [ ] **Reviews:** stars and a number show under the title, and clicking them scrolls down to the "Loved by gift-givers" section. The summary count equals the total reviews across the whole line.
- [ ] **Reviews after switching:** switch options a few times. The Judge.me carousel stays visible, and its arrows still work.
- [ ] **Not affected:** bundles and any product not in a group look and work exactly as before. For a bundle, the stars and summary show that bundle's own rating.

**Report back** with anything that looks off, plus screenshots.

---

## Step 8 — Go live
- [ ] After sign-off, the developer merges the theme change into the live theme's branch. The groups work as soon as it's live.

---

## Also changed on the product page
- The **Variant picker** block was added, which is where these buttons render.
- The **Quick order list** section was removed.
- A **star rating** block was added under the title, and a **Product reviews** section was added above Related products.
- Related products is unchanged. Siblings may show there.

## Not included
- The 8 bundles
- Collection page layout and filters

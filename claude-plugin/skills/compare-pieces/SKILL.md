---
name: compare-pieces
description: Compares two to four original artworks from Fold Laboratories side by side on medium, dimensions, artist and price, with availability, delivery and returns. Use when a buyer is choosing between works they have seen, or asks how pieces differ.
---

# Compare pieces

Set two to four works side by side so the buyer can choose. Follow agent-buyer-guide throughout.

## 1. Fetch each work

Identify the works by `artwork_id`, from earlier results or by finding the ones the buyer names with `search_artworks`. If there are more than four, ask which to compare.

Call `get_artwork` for each. If the buyer gave a ZIP code, also call `get_delivered_quote` for each work's `listing_id`.

## 2. Set them side by side

Build one table with a column for each work and these rows, in this order:

1. Title and artist, in the seller's words
2. Medium and surface
3. Dimensions: height × width × depth in inches, as stated, and whether it is framed (a frame adds to the size)
4. Year, and the edition: the `impression` label exactly as given (a unique work, 3/25, AP)
5. Price for each impression, and its availability
6. Delivery: the seller's charge and method; with a quote, the ships-by date, the arrival window and the delivered total
7. Returns: final sale, or the returns the record states
8. The seller, and whether Fold verified the seller's identity, as `verification` says (Fold verifies sellers, not works)

Write "not stated" where a value is null. Never estimate it. Keep the seller's words as theirs.

## 3. Say what differs

After the table, write a few plain sentences on the real differences: size against the buyer's wall, price, delivery and returns. Don't rank the works by price level, framing, packing or documentation, or prefer one for carrying a seller's statement. Say which fits what the buyer asked for, and let them choose.

Before offering any of them to buy, call `check_availability`, then follow agent-buyer-guide to checkout.

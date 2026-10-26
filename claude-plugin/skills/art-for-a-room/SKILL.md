---
name: art-for-a-room
description: Builds a shortlist of original artworks from Fold Laboratories for a particular room. Use when someone describes a space — the wall, the furniture below it, the palette, the style they like — and a budget, and wants pieces that would suit it.
---

# Art for a room

Turn a description of a room into a short, honest shortlist of works on sale at Fold Laboratories. Follow agent-buyer-guide throughout.

## 1. Gather what the room needs

Ask only for what is missing, in one message:

- The wall: its width and height, and the furniture the work will hang above (a sofa, a bed, a sideboard) with its width and height, if there is any. Inches or centimetres.
- The palette: the room's main colours, and whether the work should match them or contrast.
- Styles and subjects they like, and any to avoid.
- The budget for the work, and a ZIP code if they want delivered prices.

Work with what they know. Never invent a measurement.

## 2. Search across sizes and styles

Run several searches, not one, and keep each result's `artwork_id`:

1. If the wall is known, call `find_artworks_for_wall` with `wall` (`width`, `height`, `furniture_width`, `furniture_height`, `unit`), the buyer's words in `query` and `max_price_usd`. Relay its size range and reasoning as Fold's rule of thumb, not a measurement of the room.
2. Call `search_artworks` two to four more times, changing one thing each time:
   - the style (`style`), and one style the buyer did not name but that suits the room;
   - the orientation (`orientation`);
   - the size, with `min_width_in`, `max_width_in`, `min_height_in` and `max_height_in` around the range the wall suits;
   - the palette (`colors`, up to four), the room's colours or their contrast.
3. When the buyer likes a result, `find_similar_artworks` with its `artwork_id` finds works that look like it.

Check `applied_filters` in every answer, and correct a misreading with an explicit filter.

## 3. Choose the shortlist

- Merge the answers and drop duplicates. Keep matches apart from `near_matches`, and offer a near match only as one, saying what it misses.
- Choose three to six works by how well they meet what the buyer asked: size for the wall, palette, style, budget. Never favour or demote a work for its price level, framing, packing, documentation or a missing statement.
- For each one, call `get_artwork`, then `check_availability` with its `listing_id` right before you present it.

## 4. Present it

For each work: the title and artist (the seller's words), the medium, the size in inches as stated (a frame adds to it), the price with its `impression` label exactly as given, and one line on why it suits this room. Show its images.

Say how many works were checked, and whether the search was exhaustive. If nothing suits, say so plainly, suggest what to relax (size, palette, budget), or offer `save_search_alert` to hear of works listed later. For delivered prices and buying, follow agent-buyer-guide.

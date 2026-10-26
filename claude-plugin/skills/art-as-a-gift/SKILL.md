---
name: art-as-a-gift
description: Helps someone choose an original artwork from Fold Laboratories as a gift for another person. Use when the buyer is shopping for someone else; it asks about the recipient, then narrows works by price and by when they would arrive.
---

# Art as a gift

Help the buyer find a work the recipient will like, that fits the budget and arrives in time. Follow agent-buyer-guide throughout.

## 1. Ask about the recipient

In one short message, ask:

- What the recipient likes: subjects, colours, styles, art they already have, and anything they dislike.
- Where it might hang, if the buyer knows. A wall size helps (see art-for-a-room).
- The budget, and whether it should include delivery and tax.
- The date it must arrive by, and the ZIP code it will go to.

Don't ask for the recipient's name, address or any other personal details. The buyer enters the delivery address on Fold's checkout page.

## 2. Find candidates

Call `search_artworks` with the buyer's description in `query`, and filters for what they said: `max_price_usd`, `subject`, `style`, `colors`, `orientation`, and `ships_to` (`country` "US" and the `postal_code`). If the answer is thin, search again with another subject or style. Keep matches apart from `near_matches`.

## 3. Narrow by price and arrival

For up to five candidates, call `get_artwork`, then `get_delivered_quote` with the work's `listing_id` and the `destination` (`country` "US", the `postal_code`):

- Price: compare the quote's total (the work, the seller's delivery charge and the estimated sales tax) with the budget. The tax is an estimate until checkout.
- Arrival: use the date the seller says it ships by and the arrival window from the quote. Leave out a work that would arrive too late, and say why. Where the seller has not stated handling or transit times, say the arrival is unknown. Never estimate it.
- Returns: read each work's returns. A work marked final sale cannot be returned for a change of mind, so say so before it is chosen as a gift. Otherwise give the returns as the record states them.

## 4. Offer and buy

Offer two to four works, each with why it suits the recipient, the delivered total, the arrival window (or that it is unknown) and the returns. When the buyer chooses, follow agent-buyer-guide: `check_availability`, then `start_checkout`. The buyer enters the recipient's address and pays on Fold's page.

Don't promise gift wrapping, a gift note or a gift receipt. Fold's tools offer none of these.

# Fold Laboratories for Claude

Find and buy original paintings, prints, photographs and sculpture from independent artists and galleries in the United States. The plugin connects Claude to Fold Laboratories' catalogue and adds four skills:

- **Art for a room**: describe the wall, the palette, the style and the budget, and Claude searches across sizes and styles and comes back with a shortlist.
- **Art as a gift**: Claude asks about the recipient, then narrows works by price and by when they would arrive.
- **Compare pieces**: two to four works side by side on medium, dimensions, artist and price, with availability, delivery and returns.
- **Agent buyer guide**: how Claude uses Fold's tools: which to call first, how to read search results and availability, and what to confirm with you before checkout.

## How buying works

Claude never takes a payment. When you choose a work, Claude checks it is still available and gives you a link to a checkout page on Fold's own site, where you enter the delivery address, review the total with sales tax and the terms, and pay. Fold delivers within the 50 US states and the District of Columbia. Fold verifies sellers, not artworks, and issues no certificates of authenticity.

## The connector

The plugin uses Fold's MCP server at `https://api.foldlaboratories.com/mcp/directory`, the same server as Fold's listing in Claude's connector directory. It needs no account or sign-in. In Claude on the web and desktop, search results and a work's details show as a gallery of cards; each card's one button opens the work's page on Fold's site.

## What the plugin runs and sends

The plugin runs nothing on your computer: no hooks, commands, scripts or local servers. It adds the four skills above, which are instructions to Claude, and one remote MCP server, Fold's, at `https://api.foldlaboratories.com/mcp/directory`. Everything Claude sends goes to that server:

- **Searching and reading works**: the words and filters of a search, the ids of works and listings, and a wall's measurements.
- **Delivered prices**: a US ZIP code. Never a street address.
- **Works that look alike**: a work's id, or a photo you give, as its web address or the image itself. Fold's server fetches the photo once, sends it to Voyage AI to compare it with works' images, and keeps neither the photo nor its address.
- **Alerts for new works**: the e-mail address you give, or a web address of yours that Fold's server will call, and the saved search. Fold keeps them until the alert ends.
- **Orders and returns**: an order's reference and the e-mail address used at checkout, or the token from its order page, and what you say about a return or claim.

Images in answers and the gallery come from `https://foldlaboratories.com`, and checkout links open there. How Fold handles this data, and who processes it, is in the privacy policy below.

## Privacy and support

- Privacy policy: https://studio.foldlaboratories.com/privacy
- Terms: https://studio.foldlaboratories.com/terms
- For agents: https://foldlaboratories.com/agents
- Support: https://foldlaboratories.com/contact

## Licence

The files in this folder are licensed under the Apache License, Version 2.0 (`LICENSE`). Copyright 2026 Fold Laboratories, LLC.

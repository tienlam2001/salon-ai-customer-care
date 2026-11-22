# Salon AI customer-care kit

## Shared picture library

This repository is the owner's shared home for generated customer-facing salon pictures. Browse [`assets/`](assets/) and its [file manifest](assets/manifest.json). Each salon has its original two-page menu, A4 hours sign, feed/story hours designs, and a single-image service summary without promotions. `salons.json` maps each salon to its matching files. Keep customer messages and inbox screenshots out of this public library.

The `*-service-menu-no-promotions.png` files are the images currently attached to Meta menu keyword replies. The `*-hours-feed.png` files are attached to hours keyword and comment replies. Updating GitHub alone does not update Meta attachments: replace them in Meta and verify delivery after each artwork change.

See [November 22 delivery checks](tests/2026-11-22-attachment-delivery.md) for live test results and limits.

Drop the `salon-agent/` folder into your repository. This download does not publish anything, change your websites, or configure a live bot.

1. Start with `AGENTS.md`. Paste it into your bot’s system instructions or explicitly load it at startup. A GitHub folder by itself does not make a bot read the files.
2. Give the bot read access to `salons.json` and `assets/`. Connect each inbox to exactly one salon ID where possible. Keep any API keys, customer details, and staff records out of this folder.
3. Ingest both pages of each menu so the bot can find service names, prices, and footnotes. Before launch, have the salon lead approve which menu revision is live and confirm any explicit, location-specific price overrides. Use the original PDFs to verify prices. Send the matching A4 menu pictures listed in `menu_images`, and refresh them when the PDF changes. If you create a searchable text index, refresh it with the original PDF whenever a menu changes; never treat sample prices as overrides.
4. Set up the channel's attachment action. Route hours requests to the single-location A4 sign and price-list requests to the single-location A4 menu pictures. If direct attachments cannot be delivered, place customer-facing copies in an authorized public location and configure verified public links. Do not substitute private repository URLs. The `public_*_url` fields start as null on purpose.
5. Try the scenarios in `tests/reply-tests.md` on the deployed bot with test inboxes. First verify text; then confirm the file actually arrives and opens. No real outreach, charges, or appointment creation for QA.

**Sources included:** the three original menu PDFs supplied by the owner, the matching individual Google-hours A4 signs, and a simple French-tip illustration. The signs reflect the regular Google listing schedule checked November 21, 2026. Check special hours on the actual date. Website hours may differ from the signs; the signs follow Google.

## A simple daily improvement habit

1. Pick one reply to improve. Write down what the guest was asking and where the answer got confusing. Remove names, phone numbers, appointment details, and anything private before using a real conversation as an example.
2. Update the right file: wording in `AGENTS.md`; approved prices in that salon’s original menu; hours or contact details in `salons.json` and, if needed, its matching sign. Note the date and the approved source.
3. Add one example to `tests/reply-tests.md`. Check that the fix works without changing another salon’s price, sending the wrong file, or making an unverified promise.
4. Commit the one change with a short message, for example “Clarify deep French estimates.” Keep the previous version in Git so you can roll back. Do not publish a bot update until you test the reply and verify the correct attachment actually arrives.

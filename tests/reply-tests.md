# Customer reply tests

Use demo conversations only. Test with the included menu revision, then repeat after changing a menu in a test copy. Assert both reply text and file delivery. These are acceptance cases to run on your bot, not results from a live deployment.

| # | Scenario | Pass condition |
|---|---|---|
| 1 | Casabella inbox: “What time do you close Sunday?” | 5 PM on a regular Sunday; attaches only Casabella A4 PDF. |
| 2 | Ecco inbox: “Are you open Mondays?” | Regular Mondays closed; attaches only Ecco A4 PDF. |
| 3 | Lovely inbox: “When do you open on Mondays?” | 11 AM per the Google-hours sign, not the website’s older schedule; attaches only Lovely A4 PDF. |
| 4 | Unassigned inbox: “Send me prices.” | One question to identify location. No menu, price, or booking link before location is known. |
| 5 | Ecco inbox: “Send the price list.” | One friendly sentence and the original Ecco PDF. No copied price catalog. |
| 6 | Known Lovely guest: “Hours and price list?” | Short hours reply and exactly Lovely’s two PDFs. |
| 7 | Lovely: “New acrylic set, gel, regular French,” with approved PDF showing $55 and $7, both applicable | Base $55, add-on +$7, starting total $62; no invented additional charges. |
| 8 | Same service with deep French; no flat fee listed | $55 starting base; possible extra confirmed by the team; no claimed $62 total or assumed $7 deep French fee. |
| 9 | “French please, how much?” | Distinguishes natural nails vs acrylic, or asks one precise question. No unqualified French price. |
| 10 | Guest wants French on toes or a bundled French gel service | Finds the applicable line; does not apply the regular hand add-on automatically or charge for included French twice. |
| 11 | Price conflicts between the approved menu and an undated social post | Uses the approved source; an unresolved conflict within approved sources is flagged and not guessed. |
| 12 | PDF missing or unreadable | Does not invent a price or use another salon’s file; gives a useful fallback. |
| 13 | Attachment function returns an error | Does not claim success or share a private GitHub URL. Uses a verified public link only if configured, otherwise gives the salon’s site or phone. |
| 14 | “Can I come in on Thanksgiving?” | Verifies special hours or says they cannot be confirmed. The regular A4 sign is not treated as holiday proof. |
| 15 | “Book me for 2” and no booking tool is enabled | Sends the correct booking link; does not claim a booking or an available slot. |
| 16 | Guest asks to compare classic and deep French | Gives a simple, accurate description and sends the optional design illustration if supported. No guaranteed final look or price. |
| 17 | Guest says their nails chipped | Shows care and offers to connect with staff. No unverified guarantee or promise of refund. |
| 18 | Menu updated in a test copy from $55 to $57 | Uses $57, not the training example; recomputes $64 if the same +$7 still applies. |
| 19 | “At a different location” on a dedicated phone number | Offers verified contact information for that location; no cross-location booking or data lookup. |
| 20 | Long customer message mixes several questions | Answers each requested detail once. Still easy to scan, no jargon, not pushy, and no unrelated add-ons quoted. |

**Release gate:** Every location, price, sum, link, and attachment check must pass. Read the replies aloud. A person unfamiliar with nail terms should be able to explain the base service, add-ons, and next step in their own words.

# Attachment delivery checks — November 22, 2026

Tests used the owner's Facebook account to send requests to the three salon pages. No customer conversations or personal screenshots are included here.

| Salon | Messenger `menu` keyword | Messenger `What are your business hours?` FAQ |
|---|---|---|
| Ecco | Passed: correct Ecco service-menu picture visibly delivered | Passed: correct Ecco hours picture visibly delivered |
| Casabella | Passed: correct Casabella service-menu picture visibly delivered | Passed: correct Casabella hours picture visibly delivered |
| Lovely | Passed: correct Lovely service-menu picture visibly delivered | Passed: correct Lovely hours picture visibly delivered |

The menu keyword response included the saved service-summary attachment. Hours were tested through the FAQ route, which returned the salon's regular-hours picture. This does not prove every natural-language variant or the separate hours keyword rule.

Meta states that custom keyword replies require at least 15 minutes of chat inactivity. Immediate repeated keyword tests may therefore be suppressed.

Instagram customer-side delivery remains unverified: the browser was signed into the Casabella business account, and switching accounts required login. Menu/hours rules were configured for both Messenger and Instagram, but enabled settings are not evidence of successful Instagram delivery. Comment-to-message delivery has not been live-tested in this check.

## Instagram follow-up

After login approval, the browser was signed into Ecco (`ecconailsspa_fl`). Sending `menu` to Casabella triggered the expected reply text, but no image appeared in the Instagram conversation. This is a failed attachment-delivery test, not a pass. Both salons' keyword responders then answered one another because the response itself contained `menu`. Ecco's service-menu reply was temporarily paused, reworded to remove trigger terms, and re-enabled on both channels; the saved change was verified. No hours test was sent in this session.

Remaining: repeat menu and hours tests for all three salons from a personal/test account with no salon automations. Do not infer Instagram attachment delivery from Messenger success or enabled settings.

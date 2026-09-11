# Travel Protect email files

## Which file to use

| File | Purpose |
|---|---|
| `email.html` | Full-content email, currently populated with sample policy data |
| `assets/travel-protect-white.png` | Email logo extracted from the supplied design |
| `index.html` | Browser review page with version and width controls; do not send as the email body |
| `design-proof.html` | Design comparison only; contains placeholders and is not a send template |
| `assets/reference-2a.png` | Original design reference used by the review page |
| `missing-link.html` | Preview explanation for destinations that have not been supplied |

## Preview hosting

Keep the HTML files and `assets` directory together on the static host. The review page is `index.html`; `email.html` opens the email directly. After publishing, open the hosted address and check that it shows the latest version and that the logo loads. A local `127.0.0.1` address cannot be shared with a remote reviewer.

## Preparing an email for sending

1. Replace the sample name, policy number, plan,destination,travel dates, travellers, purchase date,discount and total premium with values from the policy system.
2. Replace every `missing-link.html?item=...` destination with the approved URL listed in `REQUIRED-INPUTS.md`.A preview explanation page is not a working policy or document destination.
3. Replace `assets/travel-protect-white.png` in the email with the public HTTPS URL of the hosted logo. Relative paths work on the preview website but are not a portable image source in sent email.
4. Add the actual document attachments using the sending platform. HTML alone does not attach files. Make sure the introductory sentence about attachments matches the real delivery process.
5. Import the HTML as the message body using the sending platform's HTML/template feature. Keep the inline styles,responsive style block and MSO comments. Do not use the entire browser review page as the message.
6. Set the subject and a suitable plain-text alternative in the sending platform. The hidden preheader is already present in the HTML; keep it consistent with the documents actually provided.
7. Send test messages to controlled test inboxes before sending to policyholders. Confirm content, mobile layout,logo loading and all destinations.

The email files do not configure the sender account, delivery service,attachments or policy-data integration. Those steps depend on the receiving system. See `COMPATIBILITY-REPORT.md` for the implementation choices and the limits of testing performed.

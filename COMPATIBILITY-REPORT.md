# Travel Protect — 2A HTML email

## Design and content

The email follows option 2A: a navy masthead,policy number block,policy details,document links,management button and assistance section.

The existing email was reviewed before implementation. Its disclaimer is retained,including the administrator, underwriter and representative details. Purchase date, discount, total premium, Robin Assist contact information, the claim action and Privacy Policy are also retained. These additions make the full email longer than the design sample. The scenic image from the old email is omitted because it is not part of 2A.

The policy values displayed in the preview are examples. The design comparison is a separate reference view; its legal and contact placeholders must not be used in a sent email.

## Compatibility decisions
- **Layout:** presentation tables provide the main structure. The container is fluid with a maximum width of 600 px. Conditional MSO tables provide fixed widths for classic Outlook.
- **Mobile:** the detail columns use fluid inline-block wrappers containing tables,so they can wrap when space is limited. A media query below 481 px reduces side padding and heading size and makes the columns full width.
- **CSS:** essential colours, dimensions, typography and spacing are inline. Responsive rules remain in the head. The email does not depend on external stylesheets,JavaScript or webfonts.
- **Outlook:** As mentioned earlier, I am avoiding flex/grid due to past issues; using tables minimizes these problems. The update includes resetting MSO spacing and configuring 96-DPI settings. The button utilizes a table and an anchor with a solid background. Classic Outlook may display square corners instead of slightly rounded ones; the clickable area still needs to be verified in the actual application.
- **Typography:** headings use the geometric font stack specified in the design,with fallbacks. Outlook is given an Arial fallback. Different installed fonts may change line breaks and spacing.
- **Images and links:** the logo has explicit dimensions and alternative text. The email content remains live text. Telephone and email links match the visible contact details.
- **Dark mode:** explicit colours and light colour-scheme metadata express the intended appearance. They do not guarantee that an inbox will preserve every colour in dark mode.

## Validation performed

During development,the email was checked in a Chromium browser at desktop and mobile viewport widths of 1024, 600,390 and 320 px. The desktop email container reached 600 px. Additional browser checks covered missing head styles,unavailable images and unusually long names and policy numbers. No horizontal overflow remained in those checks.

Source checks covered HTML structure, presentation-table roles,logo dimensions and alternative text,retention of important content and the disclaimer,and the absence of scripts or forms in the email.The restored local email was reviewed separately

These are browser and source checks, not delivery tests. No actual Gmail,classic Outlook, new Outlook, Apple Mail,mobile inbox or dark-mode inbox test is claimed. Pixel-for-pixel equality across all devices and inboxes has not been established.

## Before live use

Replace the sample policy values and placeholder destinations. Host the logo at an accessible HTTPS address and replace its relative image path. Supply the actual policy attachments, or revise the sentence about attached documents if the sending workflow provides links only.

Send a test through the intended delivery platform and check the agreed inboxes, including link behaviour,images blocked, mobile wrapping and dark mode. Record the actual client/version and result. The current files are suitable for design review; production sending remains dependent on these configuration and validation steps.

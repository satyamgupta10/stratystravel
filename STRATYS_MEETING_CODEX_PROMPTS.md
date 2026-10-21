# Stratys Website — Codex Prompts from the July 29 Review

These prompts were prepared from the July 29 meeting transcript and cross-checked against `stratys-homepage-latest.html`. Run them one at a time, in order. Each prompt tells Codex to inspect the current implementation first because several requests may already be partially implemented.

## Shared instruction to add to every website prompt

```text
Work only in /Users/satyamgupra/Documents/stratys-site/stratys-homepage-latest.html and its existing local asset folders. First inspect the current HTML, CSS, and JavaScript for the section named below. Preserve the established Stratys visual language, typography, colors, responsiveness, accessibility, and existing behavior that is not explicitly changed. Do not rewrite page copy unless the prompt supplies replacement copy. Do not invent URLs, savings figures, lead-capture endpoints, or third-party data. Reuse existing code patterns and CSS variables where practical. Avoid adding a framework or external dependency.

After implementation, test at desktop, tablet, and mobile widths; test keyboard interaction and prefers-reduced-motion where animation is involved. Report exactly what changed, which requirements were already present, and any content or asset still needed from the client.
```

---

## Website implementation prompts

### Prompt 1 — Navigation behavior and labels

```text
Audit and finish the Stratys primary navigation.

Requirements:
- Keep the navigation visually compact/narrow rather than spreading it across the full viewport.
- Use the approved section links and labels: Testimonials, Strategy, Savings, Services, and FAQ.
- The Home link must not appear while the visitor is at the top/hero. Once the visitor has scrolled down, Home may become visible so they can return to the top.
- Every link must scroll to the correct homepage section even after the visitor has opened and returned from a service-detail view.
- Preserve the mobile menu and ensure its expanded state, focus handling, and aria attributes remain correct.
- Do not add new navigation items.

Acceptance checks:
1. At initial page load, Home is hidden and the other five items are visible on desktop.
2. After scrolling below the hero, Home becomes available without causing a disruptive layout jump.
3. All links land on the correct sections on desktop and mobile.
4. Keyboard focus remains visible and the mobile menu closes after a selection.
```

### Prompt 2 — Hero composition and video-thumbnail controls

```text
Refine the homepage hero layout using the final approved hero asset supplied separately. Do not generate or choose the image in this task.

Requirements:
- Keep Mount Otemanu's peak inside the frame and show multiple fully visible overwater villas. It is acceptable to crop some of the resort foreground or lower edge.
- Do not mirror the image. Use the source's natural orientation.
- Prevent the headline, supporting copy, CTA, and video thumbnail from obscuring the most distinctive villas.
- If necessary, slightly reduce the headline size or adjust its width/line breaks, but preserve its impact and exact wording. Prefer a clean single-line treatment for “Your Done-For-You Points Operating System” when the viewport can support it; allow a deliberate responsive wrap when it cannot.
- Slightly reduce or reposition the hero video thumbnail only if needed to reveal the background's key subjects.
- Make the circular ring around the video play button smaller so it does not collide with the “Founder, Stratys” text. If reducing the ring is insufficient, reduce/reposition the thumbnail caption text as the fallback.
- Keep the down-arrow cue and existing CTA behavior.
- Add a readable overlay/contrast treatment only as strong as necessary; do not wash out the real destination photography.

Acceptance checks:
1. Peak and recognizable villas are visible at common laptop widths.
2. No headline, card, or play ring collisions occur.
3. The image is not mirrored or implausibly cropped.
4. The hero remains legible and balanced at 1440, 1024, 768, and 390px widths.
```

### Prompt 3 — “As Featured In” infinite logo carousel

```text
Convert the secondary “As Featured In” logo row into a smooth, continuously looping carousel.

Requirements:
- Remove the visible scrollbar and remove the left/right arrow-button dependency from the normal presentation.
- The row should move automatically in a seamless infinite loop with no visible jump at the reset point.
- Add the missing How-To podcast/publication logo and make it the center item in the initially visible desktop group.
- Pause the automatic movement while a desktop user hovers over the carousel or while keyboard focus is inside it; resume after interaction ends.
- On touch devices, allow natural horizontal swipe/drag interaction and do not rely on hover.
- Logo order must remain stable and every logo needs useful alt text.
- Respect prefers-reduced-motion: show a static, scrollable row rather than auto-animating.
- Do not use AI-generated or altered publication logos. Use the official supplied logo asset.

Acceptance checks:
1. How-To is centered on initial desktop view.
2. The loop is seamless for at least two full cycles.
3. Hover/focus pauses it; touch swiping works; reduced-motion disables autoplay.
4. No visible scrollbar or layout shift remains.
```

### Prompt 4 — Testimonial carousel, savings badges, and playback

```text
Finish the client testimonial/video carousel.

Requirements:
- Keep the carousel automatically scrolling, but pause it when a desktop visitor hovers over a testimonial and when focus is inside a testimonial.
- A click/tap on a testimonial video should open or play that testimonial immediately using the existing modal/player flow.
- Add a savings badge to the upper-left corner of every testimonial card. Use a subtle translucent blue-green circle or soft oval consistent with the Stratys palette. Format it as a small “SAVED” label plus a prominent dollar amount.
- Do not invent the dollar amounts. Create a clear data field/placeholder for each card and list the missing values in the handoff if Elliot has not supplied them.
- Ensure the badge remains readable over different photos without hiding faces or critical content.
- For Joey Katona's card, use the cleaned thumbnail supplied separately without the existing “Surprising my wife…” banner so it does not compete with the new “Saved $25,000” badge.
- Do not add links from testimonial cards to clients' LinkedIn profiles; that idea was discussed but not approved.
- Preserve keyboard navigation, modal closing, and reduced-motion behavior.

Acceptance checks:
1. Hover/focus reliably pauses movement and playback is easy to start.
2. Each card supports a unique savings amount without duplicated hard-coded markup.
3. Joey's badge and thumbnail contain no redundant $25,000 message.
4. Mobile cards remain readable and tappable.
```

### Prompt 5 — Strategy/before-and-after section micro-alignment

```text
Polish the strategy/before-and-after comparison section without redesigning it.

Requirements:
- Keep the section compact and preserve the approved before/after drag interaction and gentle glow.
- Align the top of the paragraph beginning “The reward system favors those who know how to use it” with the top edge/content baseline of the comparison box. The adjustment should be subtle.
- Remove the unexplained vertical line connecting the comparison box to the button.
- Preserve the final “You Earn / You Get / You Spend” treatment.
- Interaction should stop responding to automated invitation movement once the visitor starts dragging; the user's position must remain in control.
- Preserve responsive behavior and reduced-motion support.

Acceptance checks:
1. Paragraph and comparison box feel optically top-aligned.
2. No vertical connector remains.
3. The comparison slider still works with mouse, touch, and keyboard.
```

### Prompt 6 — Four-step process interaction and stale details

```text
Audit and finish the four-step process section (Audit/Design/Implement/Enjoy, or the current equivalent labels).

Requirements:
- Do not show separate previous/next arrow buttons. Visitors should switch steps by clicking/tapping the numbered step controls.
- Use step numbers, not percentages, in the progress/navigation treatment.
- Keep the destination label in its approved position and preserve the raw imagery without the old blue gradient.
- Ensure the selected step is visually obvious and reflected with correct aria state.
- In any booking/passport mockup text, replace visibly stale 2025 dates with believable future dates such as 2028. Do not change real legal/identity information or create a usable travel document.
- The passport graphic must have believable U.S. passport proportions: it should be more rectangular and should not extend too far to the left of the “P”. Use the corrected asset supplied separately if the fix is image-based.
- Audit every process illustration for obvious AI artifacts, malformed text, anatomy errors, duplicate objects, or impossible UI.

Acceptance checks:
1. All four steps are reachable by mouse, keyboard, and touch.
2. No previous/next arrow controls or percentage labels remain.
3. No obvious 2025 date or malformed passport proportion remains.
4. The section still fits cleanly without shrinking its readable text just to force everything above the fold.
```

### Prompt 7 — Savings calculator hierarchy and animation

```text
Implement the final approved behavior and alignment for the interactive savings calculator.

Layout and content:
- Default/minimum monthly spend is $20,000; maximum remains $500,000 unless the current calculator logic specifies otherwise.
- Remove the redundant endpoint labels “$20,000 per month” and “$500,000 per month” from around the slider. The selected value already communicates the amount.
- In the first four boxes, align all titles on the same horizontal baseline: Monthly Spending, Yearly Points Earned, Business Class Flights, and Luxury Hotel Nights.
- Use the same title font size, number font size, padding system, and vertical rhythm across those four boxes. Align $20,000, 600,000, 4, and 10 on a common visual baseline where possible.
- Keep the slider inside the first box, positioned in the remaining space below the value without crowding it.
- Keep the fifth Yearly Travel Savings box vertically centered but visually dominant. Set its result value in the approved neon/aqua blue, keep it on one line, and enlarge it only enough to stand out (start around 10%; never allow wrapping or overflow).
- Preserve the gentle pulse already used on the result card.

Intro animation:
- On the calculator's first entrance into view, animate the slider slowly from $20,000 to approximately $45,000 over about 2.5–3 seconds so the dependent values visibly update.
- At $45,000, stop the travel animation and give the slider thumb a subtle pulse/invitation animation to communicate that it can be dragged.
- As soon as the visitor clicks, drags, taps, or uses the keyboard on the slider, cancel all invitation animation permanently for that page visit and give full control to the visitor.
- Do not add “Drag me” copy initially.
- Disable the intro/pulse under prefers-reduced-motion and avoid replaying it every time the section re-enters the viewport.

Assumptions:
- Keep one compact expandable Assumptions disclosure.
- Move the statement about Stratys clients maximizing business spending at 2.5 cents per point into that disclosure as its first bullet; remove its separate standalone box.
- Preserve the other calculation assumptions and the accessible calculator summary.
- Do not change the formulas unless necessary to keep the displayed outputs synchronized.

Acceptance checks:
1. Initial animation runs once, slowly, from $20k to about $45k.
2. User interaction cancels animation immediately.
3. All values and aria-valuetext update correctly.
4. Titles and values align; the final savings result is the strongest visual element without wrapping.
5. The removed disclosure box shortens the section cleanly.
```

### Prompt 8 — Services overview header and card layout

```text
Refine the homepage Services overview layout.

Requirements:
- Move the paragraph beginning “We work with a select number of clients each year…” to the left side so it reads as supporting copy attached to the “Travel, elevated beyond expectations” heading.
- Use the same body/description font size as comparable supporting copy elsewhere on the homepage (for example the paragraph beneath the prior major section heading). The paragraph should not look smaller or isolated.
- Remove the vertical divider between the heading area and that paragraph if it prevents the copy from reading as one unified header block.
- Keep the section compact and retain both service cards in the same section viewport where reasonable, without making the body text too small.
- Keep only the service labels “Full Service” and “A La Carte” over their respective card imagery; do not add “Stratys Travel Concierge” as extra image-overlay text.
- Integrate the separately approved Prague and business-class assets using deliberate, responsive object positioning.

Acceptance checks:
1. Heading and supporting paragraph read left-to-right as one group.
2. The paragraph uses the site's normal supporting-copy size.
3. No unnecessary vertical divider remains.
4. Card labels are concise and images crop safely across breakpoints.
```

### Prompt 9 — Service cards and “View highlights” separator

```text
Polish both service overview cards' expandable “View highlights” area.

Requirements:
- Preserve the approved subtle aqua accent animation that expands on hover/focus.
- Make the thin top separator above “View highlights” extend fully from the left edge to the right edge of each card.
- Remove the bottom separator line below “View highlights.” The top rule should make the row read like a footer banner attached to the card.
- Reduce any excess empty space under the row so the bottom of the card feels intentional.
- Apply exactly the same treatment to the Full Service/Concierge card and the A La Carte/Premier Award Booking card.
- Preserve the ability for both cards to be open simultaneously, the existing label change between “View highlights” and “Hide highlights,” and correct aria-expanded/aria-hidden state.

Acceptance checks:
1. Both cards have one full-width top separator and no bottom separator.
2. Expanded content is not clipped and card height transitions smoothly.
3. Hover, focus, click, and touch states remain clear.
```

### Prompt 10 — Concierge detail page alignment and pricing tiers

```text
Refine the Full Service / Stratys Travel Concierge detail page.

Hero requirements:
- Use the separately approved Japan hero asset.
- Align the top of the image with the top of the primary heading, not with the eyebrow/tag above the heading. Apply the same image-to-heading alignment convention used elsewhere on the site.

Pricing-tier requirements:
- Keep the existing different light-blue background shades for Standard, Pro, and Enterprise expanded areas; do not remove the two-tone shading.
- At the boundary between the top summary portion and the lighter expanded-content portion, add a very thin aqua horizontal divider using the same accent color as the card border/site rules.
- Move “Includes” and the following inherited-feature content down enough to create visible breathing room below the divider (roughly the visual effect of about 1 cm on desktop, but implement responsively rather than as a literal physical unit).
- Reduce the large gap between “Includes” and the first feature (“Point Strategy,” etc.) so the inherited-content block reads as one group.
- Keep all tier accordions and the comparison accordion functional and accessible.

Acceptance checks:
1. Hero image top aligns with heading top.
2. Shading remains and the thin divider clearly separates the two tones.
3. “Includes” is not pressed against the divider and is not detached from its list.
4. All tiers work on desktop/mobile and through keyboard navigation.
```

### Prompt 11 — Golden Rules lead-capture alignment and feedback

```text
Finish the “The Golden Rules of Points” lead-capture band on the Concierge detail page.

Requirements:
- Vertically center the email input and “Get the Guide” button group against the guide title/content on the left. In the untouched/default state, both sides should share a clean visual centerline.
- Reserve enough status-message space that focusing, validating, or submitting the form does not push the controls upward or make the band jump.
- Invalid email state: show a small inline message below the field, such as “Please enter a valid email address.”
- Success state: keep the form/band in place and show a small inline confirmation below the field. Use dynamic text that repeats the submitted address, e.g. “Please check your inbox at name@example.com for the guide.”
- Do not replace the whole section, collapse the form, or show a full-screen success takeover.
- Use small, secondary text—approximately the visual weight of existing asterisk/help copy—not a large headline.
- Preserve the entered address on errors, prevent duplicate submissions while a request is in flight, and expose status changes to screen readers with an appropriate live region.
- If the production endpoint is still unavailable, keep the integration clearly marked and do not fake a successful network request.

Acceptance checks:
1. Default, error, loading, and success states do not cause a vertical jump.
2. Success text repeats the submitted email.
3. Keyboard focus and screen-reader announcements work.
```

### Prompt 12 — Footer/social brand icons

```text
Replace any blurry, AI-altered, or unofficial Trustpilot, LinkedIn, and YouTube marks with clean official brand assets supplied or downloaded from their official brand-resource pages.

Requirements:
- Do not generate these logos with AI and do not redraw approximate versions.
- Preserve the approved existing presentation: icon centered inside the current circular treatment, with consistent sizing, stroke/edge clarity, spacing, and hover/focus styling.
- Use SVG where licensing and the local architecture allow; otherwise use high-resolution transparent PNG assets.
- Supply meaningful accessible labels for the links while treating decorative icon artwork appropriately.
- Do not invent destination URLs. Keep existing URLs or flag any missing link for the client.

Acceptance checks:
1. All three marks are crisp at normal and retina resolutions.
2. Circle sizing and alignment are consistent.
3. Links and focus states remain accessible.
```

### Prompt 13 — Founder and FAQ verification

```text
Verify the approved Founder and FAQ states, making only corrections that are still missing.

Founder:
- Keep the approved real Norway travel photo of Elliot. Do not replace or AI-edit it.
- Preserve its role in showing that Stratys is about destinations and experiences, not only flights and hotel rooms.

FAQ:
- Load the page with every FAQ item collapsed; the first item must not be open by default.
- All collapsed question rows should have a consistent control height and vertical alignment. Allow wrapping text to use the space it needs without clipping, while retaining a consistent minimum height.
- Opening one item must not break the layout, focus order, plus/minus indicator, or scroll behavior.

Acceptance checks:
1. Founder image is the approved real photo.
2. No FAQ is expanded on load.
3. FAQ controls look consistent and work with keyboard and screen readers.
```

### Prompt 14 — Contact/inquiry form fixed height and validation

```text
Stabilize the multi-step “Ready to travel differently?” inquiry form.

Requirements:
- Keep the form container at a consistent visual height while moving among steps 1, 2, and 3 so it does not randomly expand or contract. Determine the tallest normal step at the current breakpoint and reserve an appropriate responsive minimum height; do not create excessive empty space on narrow mobile screens.
- Keep headings, progress indicators, fields, and navigation buttons aligned consistently between steps.
- Preserve existing required-field validation and ensure email uses real email-format validation with a clear inline error.
- Validation errors must not overlap fields or cause a large page jump.
- Preserve entered values when navigating backward and forward.
- All homepage and service-page “Get Started” CTAs should open/navigate to this form correctly and focus the first relevant field or heading.
- Keep submission feedback inside the form and expose it through a live region.

Acceptance checks:
1. Switching among all steps does not produce a jarring height change at desktop/tablet widths.
2. Mobile height can grow naturally where needed without clipped content.
3. Invalid email, missing required radio choices, back/next navigation, and submit states work.
4. CTA-to-form navigation works from the homepage and both service-detail views.
```

### Prompt 15 — Final regression and visual-quality pass

```text
Perform a final regression pass on stratys-homepage-latest.html after the July 29 changes.

Do not redesign or rewrite copy. Check and correct only regressions related to the approved work:
- navigation visibility and anchors;
- hero crop, text/media overlap, and CTA;
- featured-logo and testimonial autoplay/pause behavior;
- strategy comparison and four-step process interactions;
- savings calculator math, one-time animation, alignment, and assumptions;
- services overview, service-card accordions, and detail-page navigation;
- Golden Rules form states;
- pricing tier separators and spacing;
- Founder/FAQ default states;
- contact form height and validation;
- footer icons and links.

Test at 1440×900, 1024×768, 768×1024, and 390×844. Test keyboard-only navigation and prefers-reduced-motion. Check the console for errors. Confirm no text is clipped, no horizontal overflow occurs, no interactive control is unreachable, and no image critical subject is covered. Return a concise pass/fail checklist and identify any blocker that requires client-supplied copy, URLs, savings amounts, or licensed images.
```

---

## Separate image and asset prompts

### Image Prompt A — Hero image sourcing and crop plan (use real photography, not AI generation)

```text
Find or select a legally usable, high-resolution, real photograph for the Stratys homepage hero. The scene must show Bora Bora with Mount Otemanu, turquoise lagoon water, palm trees, a small area of white sand, and recognizable overwater villas in one coherent panoramic composition. The geography and perspective must be physically believable.

Composition for the website:
- wide landscape hero, ideally 16:9 or wider with enough resolution for a full-width desktop crop;
- Mount Otemanu's peak fully visible with some sky above it;
- several overwater villas completely visible, not all hidden behind the future text/video overlay;
- foreground may be cropped, including part of a bridge or resort edge;
- ideally place darker visual detail on the left and calmer/lighter negative space on the right, or provide enough width to crop around the website overlay;
- natural light and premium editorial travel photography; no heavy HDR, surreal saturation, fake architecture, or visible brand watermark.

Do not use AI-generated photography for this homepage hero. Return the source/license information, original dimensions, and two recommended object-position/crop coordinates: desktop and mobile.
```

### Image Prompt B — Elliot hero video thumbnail edit

```text
Edit the supplied original photograph of Elliot Rosenberg for a website video thumbnail. Preserve his real face, hairline, skin texture, expression, proportions, suit, and age exactly. Remove the original background cleanly and place him over the approved Stratys thumbnail background. Do not regenerate his face or body, do not smooth skin, do not add hair, and do not add artificial rim light or glowing shoulder highlights.

Keep edge detail natural around hair and shoulders. Leave clear negative space for the exact text “Founder, Stratys” and for a small circular play icon. The play icon and its ring must not overlap the text. Deliver a high-resolution PNG/WebP plus a transparent-background cutout of Elliot for future layout adjustments.
```

### Image Prompt C — Joey Katona testimonial thumbnail cleanup

```text
Edit the supplied Joey Katona testimonial thumbnail only. Remove the banner/text reading “Surprising my wife for the $25,000 gift for Mother's Day” and reconstruct the covered background naturally. Preserve Joey, the original scene, lighting, crop, and realism. Do not add new text, logos, badges, faces, or decorative effects. Leave the upper-left corner sufficiently clean for the website to overlay its own translucent “SAVED $25,000” badge in HTML/CSS. Export at the same aspect ratio and at least the same resolution as the source.
```

### Image Prompt D — Four-step process passport/booking composite

```text
Edit the existing “Implement” process illustration while keeping it clearly fictional and non-usable as a document. Correct the visible passport cover so it has believable U.S. passport proportions: a vertical rectangle, not a square or overly wide shape, with less excess material to the left of the “P.” Preserve the premium flat-lay composition.

Update any clearly visible itinerary/booking year from 2025 to a plausible future example such as 2028. Keep the route concept JFK to the Maldives and the Maldives booking context if present. Use intentionally fictional/blurred personal details and booking numbers. Do not create a scannable passport, barcode, QR code, or realistic identity page. Maintain the original website image dimensions and leave all text outside the graphic to HTML.
```

### Image Prompt E — A La Carte business-class card image

```text
Create a photorealistic, editorial-quality image of a modern international business-class suite inspired by top-tier lie-flat products, but without copying a specific airline's branded cabin, colors, logo, or proprietary design.

Show one empty private suite in full lie-flat bed mode from a wide three-quarter angle so the viewer immediately understands the space and privacy. Include two well-arranged pillows and a blanket. On the side table, show an elegant empty place setting with a white linen tablecloth, refined glassware, and real-looking cutlery; no food and no amenity kit. Use bright, natural, neutral cabin lighting—not purple mood lighting—so all features are clearly visible. The scene should feel attainable for a premium business-class traveler, not like a private jet, first-class apartment, train, showroom, or sci-fi concept.

No people, text, airline logos, warped furniture, impossible windows, duplicate cutlery, malformed glassware, or extra seats. Wide landscape composition suitable for a shallow website card crop, with the suite's main features inside the central safe area.
```

### Image Prompt F — Concierge/full-service Prague card image

```text
Create or select a photorealistic wide-angle editorial cityscape of Prague for the Stratys Full Service card. The scene should clearly feel like historic Prague without relying on text: river, a recognizable bridge, layered old-city architecture, church/cathedral spires, and a natural blue sky with attractive clouds. Balance urban grandeur with nature through visible water and sky.

Compose for an extra-wide, shallow website crop. The bottom third may be cropped, but retain some river and a small portion of the bridge as foreground, the city as midground, and sky as background. Do not cut off the spires or cathedral tops. Avoid overused generic European imagery, fake landmarks, warped buildings, excessive HDR, fantasy lighting, people in the foreground, or embedded text.
```

### Image Prompt G — Concierge detail page Japan hero

```text
Create or source a striking, photorealistic wide-angle Japan travel image that is recognizable instantly. Include Mount Fuji with its complete summit visible, pink cherry blossoms, and unmistakable traditional Japanese temple/pagoda architecture in one balanced composition. The image must read as Japan at a glance, not as a generic garden or hotel view.

Use realistic daylight, natural scale and geography, premium travel-editorial color, and enough sky/negative space for a wide website hero crop. Do not flatten or crop Mount Fuji's summit. Avoid collages, hotel-room foregrounds, fantasy architecture, text, tourists dominating the frame, oversaturation, or visible brands.
```

### Image Prompt H — Premier Award Booking luxury overwater-villa hero

```text
Create a photorealistic, ultra-premium overwater-villa interior that communicates a rare, bookable travel experience rather than a standard hotel room. Use a wide interior angle that captures, in one coherent room: a glass-bottom floor panel revealing clear tropical water, a luxurious bed facing the ocean, a soaking tub, an infinity pool/terrace, an overwater lounge area, and a glimpse of a generous living area. The architecture and reflections must be physically plausible.

Style: warm contemporary luxury, aspirational but believable, premium hospitality editorial photography, natural tropical daylight, refined neutral materials, no specific hotel or resort branding. It should feel spacious and “wow” without looking like CGI. Keep the central subject matter safe for a wide website crop.

Avoid fisheye distortion unless extremely subtle, impossible floor/water geometry, duplicate furnishings, floating objects, malformed glass, text, logos, people, gaudy decor, or an unbookable fantasy concept. If the combined scene cannot be made convincing, prioritize the glass-bottom floor, ocean-facing bed, soaking tub, and infinity pool.
```

### Asset Prompt I — Official logos (not for an AI image generator)

```text
Collect the official current Trustpilot, LinkedIn, YouTube, and How-To podcast/publication logo files from the organizations' official brand/resource pages or from client-supplied originals. Prefer SVG; otherwise obtain high-resolution transparent PNG. Record the source URL and any usage restrictions. Do not trace, stylize, “enhance,” or generate these marks with AI. Prepare normalized exports with consistent optical sizing while preserving every logo's required clear space and colors.
```

---

## Items intentionally not converted into implementation prompts

- Linking testimonial clients to their personal LinkedIn profiles was debated but not approved.
- New page copy was still pending from Elliot, so no copy rewrite should be invented.
- Testimonial savings amounts other than the stated Joey example need to be supplied by Elliot.
- Production endpoints and missing footer destinations must be supplied/confirmed rather than fabricated.
- The approved Norway founder photo should remain unchanged.


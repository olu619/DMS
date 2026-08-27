# MEMORY

---

## Preferences

### Communication Style
- Olu describes himself as a layman when it comes to technical concepts – always explain what something does AND why it's being used in that specific situation, not just what it's called
- If a technical term has to be used (e.g. "pixel", "workflow trigger", "DNS"), follow it immediately with a plain-English explanation in brackets or a short sentence. Example: "a pixel (a tiny invisible piece of code that tells Meta who visited your page)"
- Never omit information in the name of simplicity – simplify the language, not the content
- Direct, no-fluff tone. Get to the point. No preamble before the output
- Prefers exact, specific values – hex codes, font sizes, pixel dimensions, GHL field names, step counts – not vague guidance
- Outputs preferred as interactive HTML artifacts or downloadable files, not Word docs (unless specifically asked)
- Short responses for simple tasks. Longer structured output only when the task genuinely requires it
- Iterates heavily across multiple rounds – always apply all previous refinements cumulatively, never reset

### Format
- Bullet points for lists and rules. Prose for explanations
- When building GHL systems or HTML: provide the exact values to enter, not a description of what to look for
- For carousels and social content: deliver the full HTML file + the ready-to-paste Meta caption in the same output
- Corrections and suggestions should be flagged clearly and briefly – never buried inside a long response

---

## Corrections

- **Don't use "straightforward"** – flagged as a word to avoid in all outputs
- **Nav Menu widget in Elementor requires Elementor Pro** – the free version doesn't include it. Correct workaround: use the Hello Elementor theme's built-in Customizer header instead (Appearance → Customize → Header). This came up during Sammy's website build
- **£5/day Meta ad spend is too low** to seed retargeting audiences at a useful speed. Correct baseline is £8/day (£240/month). The retargeting audience (Campaign 2) needs enough people flowing in from Campaign 1 first – at £5/day that takes too long
- **GHL form build sequence must follow this exact order:** (1) Create custom fields in Settings → Custom Fields first, (2) then build the form in Marketing → Forms, (3) then build the workflow in Automation → Workflows triggered by that form submit, (4) then embed via Form Widget on the funnel page. Doing these out of order causes the form and workflow to not connect properly
- **Google Drive connector in this environment is currently read-only** – it can search and retrieve files but cannot upload. Always inform Olu to drag files in manually rather than silently failing

---

## Patterns

### GHL Builds
- Always follow the build sequence: Custom Fields → Form → Workflow → Embed on page
- Automation build order across the 7 planned workflows: 01 → 02 → 03 → 04 → 05 → 06 → 07
- Automation 01 (Lapsed Lead Re-Engagement) is built. Always reference `GHL_Automation01_Full.docx` as the style template for all subsequent automation builds
- Lead scoring logic: Patients (max 3pts) + Revenue (max 3pts) + Timeline (max 3pts) = 9pts max. Hot = 7–9, Warm = 4–6, Cold = 0–3

### Social Content Workflow
- Always follow the three-phase pipeline from the chiro-content-engine skill: Research → Script → Design
- Always read `Dynamo_ICP_PainPoints.docx` before writing any content – this is the primary reference for pain points, language patterns, and content angles
- Default to Tier 1 (clinic owners) for all paid ads and content. Tier 2 (e.g. martial arts, beauty) only enters via organic content using Karoon Taekwondo as the bridge proof point
- SPCL framework governs all copy: P (Power/actionable), S (Status/aspirational), C (Credibility/proof), L (Likeness/mirror – always woven in, never standalone)
- Default weekly rhythm: Monday P, Wednesday P or S+C, Friday P or S+C, Sunday Carousel P

### Carousel HTML Output
- Cover h1: 124px. Content slide h1: 96px. Body: 44px / line-height 1.5
- `.content-inner` uses position:absolute; top:60px; left:52px; right:52px; bottom:200px; overflow:hidden – this prevents text from overlapping the badge and brand name at the bottom
- Badge sits at bottom:90px left:52px – outside `.content-inner`
- Brand name ("Dynamo Media Solutions") sits at bottom:32px right:52px – outside `.content-inner`
- Logo top-right on every slide (centred on the CTA slide)
- No SVG icons by default
- Always replace `LOGO_PLACEHOLDER` with actual base64 string from assets/logo-b64.txt

### Client Pitching
- For non-technical clients or clients happy with their current system (e.g. Zitavy): lead with zero disruption. Build the new system separately first, demo it, then switch – never imply their current setup is broken
- Key framing: "Nothing changes until you're ready"
- For cold outreach: always lead with the free Patient Leakage Audit (Offer 00) as the door-opener before introducing paid offers

### VSL Filming
- Office scenes: 1, 2, 2B, 2C, 3, 4, 6, 7 (talking head only)
- Home session: Scene 5 only (GHL screen share via Loom, with picture-in-picture face cutout)
- Film office scenes in warmup order – Scene 1 last
- Continuity checklist: same outfit, matching lighting colour temperature (warm vs cool – pick one and stick to it), consistent audio setup, same camera framing across both locations

---

## Decisions

### Positioning & Pricing
- No hard outcome guarantees at Stage 1. The Founder Rate (£500–£800) trades discounted setup for honest testimonials – this is intentional and must not be reframed as a results guarantee in any copy or pitch
- Paid ad campaigns do not launch until: (1) VSL is recorded, and (2) Sammy's written permission to use the tripled bookings result is confirmed. Verbal permission exists but is not enough for public use
- The tripled bookings stat is the central proof point for all paid ads and the VSL – everything waits on written sign-off

### Funnel Architecture
- Capture-first structure is fixed. The funnel always starts with a short capture page (name/email/phone) before the VSL – not the VSL directly. This is because: GHL needs a contact record to trigger automations, and Meta's Pixel needs a known identity to attribute ad conversions. Without the capture page first, both systems break
- Capture page spec: dark navy background (#07112B), single column, max 480px wide, mobile-first, no nav links, no video, no testimonials, no pricing. One job: collect name/email/phone and redirect to VSL page

### Sammy (Karoon Taekwondo)
- Booking system: 6 separate GHL Class Booking calendars (one per class type per location) – this is the correct structure for one instructor running two venues. Google Calendar must be connected to GHL with conflict checking enabled so Sammy doesn't get double-booked
- Homepage: Version 3 design confirmed (white/blue, Playfair Display headings, parent-friendly aesthetic)
- Pricing: £45/month for weekly sessions, free trial first
- Sammy's chiropractic clinic is a separate project – do not combine with the Taekwondo Academy work

### Brand & Audience Language
- Always say "clinic owner" or "private clinic" – never chiropractor-specific – unless the brief explicitly targets chiropractors only. The ICP covers physios, osteopaths, and sports rehab coaches too
- Typography is fixed: Playfair Display for all headings, DM Sans for everything else. Both are free Google Fonts available in GHL's font picker
- Brand colours are fixed: Gold #E9D695, Blue #4D606E (carousels/social), Navy #07112B (capture page)

### Dynamo Instagram
- Account was previously an inactive meme page, rebranded to Dynamo business page – ~15K followers
- A second scratch account is running as a control (averages ~40 views per reel) – keep this in mind when comparing performance
- Best performing reel so far: 613 views. Majority of views from non-followers – good reach signal
- Current lever: volume and consistency, not polish. Post more, learn faster

### Tools
- Elementor free is the confirmed choice for Sammy's site – Elementor Pro is not in use. Never recommend Pro-only features (e.g. Nav Menu widget) as a solution
- Poptin is the confirmed popup tool for Sammy's booking UX – 6 buttons map directly to 6 popups (single-click), not a two-step chain
- SVG uploads in WordPress require the "Safe SVG" plugin – without it WordPress blocks SVG files for security reasons. Use Image widgets in Elementor (not Icon List widget) when text is embedded in an SVG

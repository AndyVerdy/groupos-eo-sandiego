# SKILL: GroupOS Custom Sales Deck Builder

## What This Is
A playbook for creating personalized GroupOS pitch decks for prospective clients. Each deck is a standalone HTML file with CSS animations, keyboard/touch navigation, and responsive design — deployed via GitHub Pages.

## Reference Deck
`https://github.com/AndyVerdy/groupos-eo-sandiego` — EO San Diego deck (the first one built using this process).

---

## PHASE 1: Research the Organization

Before writing a single line of HTML, deeply research the target organization. This is the most important step — the deck must feel like it was built specifically for them, not a generic product demo.

### What to Research
1. **Organization structure** — Chapters, regions, member types, committees, programs
2. **Membership tiers** — Who are the different member types? (e.g., EO has Full Members, Accelerator, Spouse/Partner, Key Executive Forum)
3. **Pain points** — What tools are they currently using? (WhatsApp, Slack, Eventbrite, Mailchimp, Google Sheets, etc.)
4. **Events** — What types of events do they run? (Learning, social, retreats, conferences, board meetings)
5. **Communication channels** — How do members currently communicate? What's broken?
6. **Brand guidelines** — Logo, colors, fonts. Check for a brand portal (e.g., `brand.eonetwork.org`)
7. **Programs** — Mentorship, accelerator, forums, special interest groups
8. **Size** — Member count, chapter count, geographic spread
9. **Terminology** — Use THEIR language. EO says "Forum groups" not "mastermind groups". Other orgs may say "chapters", "lodges", "sections", etc.

### Where to Research
- Organization's main website
- Brand guidelines portal (if exists)
- LinkedIn (org page + key contacts)
- Their existing app or member portal
- Public event listings
- Annual reports or press releases
- Ask the GroupOS sales contact for intel

### Research Output
Create a brief with:
- Organization name and chapter/region being pitched
- Member count and types
- Current tools they use (for the "Challenge" slide)
- 3 pain points specific to them
- Key programs/event types to reference
- Brand colors (hex codes) and logo files
- Any specific terminology to use

---

## PHASE 2: Deck Structure

### Slide Order (18 slides for EO, adapt as needed)

| # | Slide | Type | Purpose |
|---|-------|------|---------|
| 1 | **Cover** | Dark | Hook — org logo + "Your Chapter. Your App. One Platform." |
| 2 | **Challenge** | White | Show you understand their pain — list their current tools, show 3 pain points |
| 3 | **Events** | White | Text left + image right (g2ti grid) |
| 4 | **Ticketing** | White | 3-column image grid (ig3) |
| 5 | **Event Experience** | White | 2-column image grid (ig2) |
| 6 | **Chats & Channels** | White | Text left + image right |
| 7 | **Direct Messages** | White | Text left + image right |
| 8 | **Video & Content** | White | Text left + image right |
| 9 | **Documents** | White | Text left + image right |
| 10 | **Monetization & Access** | White | 2-column image grid |
| 11 | **Exhibitors & Partners** | White | Text left + video/image right |
| 12 | **Partners (cont.)** | White | 3-column image grid |
| 13 | **Notifications** | White | Centered + 3 phone images |
| 14 | **Membership Tiers** | White | Text left + image right — customize tiers per org |
| 15 | **Members Map** | White | Text left + screenshot right |
| 16 | **White-Label** | White | Text left + app screenshot right |
| 17 | **Timeline** | White | 4-week launch timeline |
| 18 | **CTA** | Dark | Org logo + closing headline |

### Slide Types
- **Dark slides** (`s-dk`): Only cover and CTA. Dark background (#1a1a1a), white text, yellow accents.
- **White slides** (`s-wh`): Everything else. White background, dark text, yellow accents.

### Not Every Org Needs Every Slide
- Skip **Exhibitors & Partners** if the org doesn't have sponsors
- Skip **Monetization** if not relevant
- Add slides for features specific to the org (e.g., "Mentorship Matching" for mentorship-heavy orgs)
- The **Membership Tiers** slide MUST be customized — never use EO's tiers for another org

---

## PHASE 3: Design System

### Colors
```css
:root{
  --dk:#1a1a1a;          /* Dark backgrounds */
  --wh:#ffffff;           /* White backgrounds */
  --ylw:#F5C518;          /* Yellow accent — GroupOS brand */
  --ylw-bg:rgba(245,197,24,0.12); /* Yellow tint for backgrounds */
  --g50:#fafafa;          /* Subtle backgrounds */
  --g100:#f5f5f5;
  --g200:#e5e5e5;         /* Borders, dividers */
  --tx:#1a1a1a;           /* Primary text */
  --txm:#525252;          /* Secondary text */
  --txl:#737373;          /* Light/caption text */
}
```

### Font
**Montserrat** from Google Fonts. Weights: 300-900. Import:
```css
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700;800;900&display=swap');
```

### Font Sizes
- H1: 64px (cover), 56px (CTA)
- H2: 46px
- H3: 22px
- Body: 18px
- Subtitle: 21px
- Pill labels: 13px uppercase
- Captions: 15px
- Feature list items: 17px

### Key CSS Classes
| Class | Use |
|-------|-----|
| `.slide` | Every slide wrapper |
| `.s-dk` / `.s-wh` | Dark or white slide |
| `.g2ti` | 2-column grid (text left ~48%, image right ~52%) — main layout |
| `.g2` | 2-column grid (equal 50/50) |
| `.g3` | 3-column grid (equal thirds) |
| `.ig2` / `.ig3` | Image grids (2 or 3 cols) with captions |
| `.imh` | Hero image (full width, rounded corners, shadow, object-fit:contain) |
| `.ims` | Smaller image (rounded, lighter shadow) |
| `.pill` | Yellow category label |
| `.pill-dk` | Pill variant for dark slides |
| `.ft` | Feature list (ul) |
| `.dt` | Yellow dot bullet |
| `.pn` | Pain point card (yellow left border) |
| `.tl` / `.tl-i` / `.tl-w` / `.tl-c` | Timeline layout |
| `.ph-row` / `.ph-img` | Phone image row (notifications slide) |
| `.cta-c` | CTA centered layout |
| `.wm` / `.wm-logo` | Watermark (GroupOS logo, bottom-left) |

---

## PHASE 4: Image Sourcing

### GroupOS CDN Images
Base URL: `https://cdn.prod.website-files.com/673e4117f87b553a20b29eca/`

Key images available (append to base URL):
```
679d310dc7908524729da405_img-main-community.webp   — Cover hero (app screens)
6772b4f396dc340263623a67_img-events-head.webp       — Events dashboard
67b3366cbb9004d905872232_img_event_ticketing_multiple.webp — VIP ticket types
67b3366e21545b0a10a88855_img_event_ticketing_main.webp    — Tickets main
67b3366bb774950a51fcb5a8_img_event_ticketing_payments.webp — Mobile payments
67b3366be1a4bfe4867e6a6e_img_event_ticketing_forms.webp   — Registration forms
67882fb1662c49dc1f0fef13_img-schedule-agenda.webp         — Event agenda
67a6256814347af3989409f0_img-chats-main.webp              — Chats & channels
67a6256857b4ff80746cea16_img-chats-dms.webp               — Direct messages
676090b0873e2b6d267a55bd_img-videos.webp                  — Video library
676090b0fabb8b76bd157c76_img-docs.webp                    — Documents
67897b631b986734704112a8_img-pomotions-videos.webp        — Sponsored video
67897b6862713f068900a916_img-privacy-videos.webp          — Access control
676090b0dab4348d94ef180a_img-partners.webp                — Partners page
67a655f35cb92211f7fe3b2c_img-notifications-in-app.webp    — In-app notifications
67a655f3a11f6000c0843381_img-notifications-news.webp      — Notification feed
67a655f3bebeb177e926aba7_img-notifications-push.webp      — Push notifications
6792b0012e845051c0b89906_img-membership-main.webp         — Membership tiers
```

### Local Images (per-client)
Some slides need client-specific screenshots or assets saved locally:
- **Members Map** — Screenshot from a live GroupOS community showing the map
- **White-Label** — Screenshot of the client's branded app (if available)
- **Exhibitors video** — `Exhibitors.mp4` autoplay video
- **Partner images** — Screenshots from GroupOS partner/exhibitor features
- **Client logo** — Download from their brand portal (get white version for dark slides)
- **GroupOS logo** — `groupos-logo.svg` for watermark

### GroupOS Feature Pages to Fetch
Always fetch these pages to get accurate feature copy and discover new CDN image URLs:
```
https://www.groupos.com/events
https://www.groupos.com/event-ticketing
https://www.groupos.com/qr-codes
https://www.groupos.com/chats
https://www.groupos.com/direct-messages
https://www.groupos.com/videos
https://www.groupos.com/documents
https://www.groupos.com/partners
https://www.groupos.com/notifications
https://www.groupos.com/members
https://www.groupos.com/membership
```

### Image Rules
- All images use `object-fit:contain` — never stretch
- Use `.imh` class for hero images (shadow + rounded corners)
- Videos use `autoplay muted loop playsinline`
- Skip Facebook/social default silhouettes — use DiceBear for fallback avatars if needed

---

## PHASE 5: Customization Checklist

For each new org, customize these elements:

### Cover Slide
- [ ] Organization logo (get from brand portal)
- [ ] Pill text: "BUILT FOR ORGANIZATIONS LIKE [ORG NAME]"
- [ ] Subtitle mentioning what they are (chapter-based org, professional network, etc.)
- [ ] Stats row (keep or customize: "1 Single app", "iOS+Android", "100% White-labeled")

### Challenge Slide
- [ ] Pill: "WE UNDERSTAND [ORG NAME]"
- [ ] Headline: "Built for How Your [Chapter/Organization] Actually Works"
- [ ] Member count and programs they run
- [ ] Current tools flow (research what they use: WhatsApp, Slack, Eventbrite, etc.)
- [ ] 3 pain points specific to their situation

### Feature Slides (3-14)
- [ ] Keep GroupOS features accurate — ONLY use real features from groupos.com
- [ ] Customize examples: "Forum channels" → whatever their equivalent is
- [ ] Customize committee names: "Board, Learning, Social" → their actual committees
- [ ] Reference their specific event types

### Membership Slide
- [ ] COMPLETELY REWRITE for each org — use their actual membership tiers
- [ ] Research their programs and access levels
- [ ] Use their terminology

### White-Label Slide
- [ ] Change "EO San Diego" to their org name
- [ ] Use their app screenshot if available, otherwise use generic GroupOS mockup

### Timeline Slide
- [ ] Keep the 4-week structure
- [ ] Customize org name references
- [ ] Adjust content types mentioned (Forum → their equivalent)

### CTA Slide
- [ ] Organization logo (white version for dark background)
- [ ] Keep or customize headline

---

## PHASE 6: Technical Implementation

### File Structure
```
groupos-[org-slug]/
├── index.html           — The entire deck (HTML + CSS + JS in one file)
├── groupos-logo.svg     — GroupOS watermark logo
├── [org]-logo.png       — Client org logo (white version)
├── members-map.png      — Members map screenshot (if available)
├── eo app.png           — White-label app screenshot (if available)
├── Exhibitors.mp4       — Exhibitors video
├── partners-*.webp      — Partner/exhibitor screenshots
├── badges.webp          — Badges screenshot
├── og-image.png         — OG share image (1200x630)
└── CLAUDE.md            — Project instructions
```

### Single File Rule
**Everything stays in `index.html`** — HTML, CSS, and JS. No separate files. No frameworks. No build step.

### Navigation (JS)
- Arrow keys (left/right) and spacebar
- Touch swipe on mobile
- Click navigation buttons (bottom-right)
- Slide counter: "X / Y"
- Progress bar at top (yellow)
- Body class `dk` toggles for dark slides (nav, watermark colors)

### Deployment
1. Create GitHub repo: `groupos-[org-slug]`
2. Push to `main` branch
3. Enable GitHub Pages (serve from root of `main`)
4. Live URL: `https://andyverdy.github.io/groupos-[org-slug]/`

### GitHub Pages Workflow
Add `.github/workflows/static.yml` for deployment (or enable Pages in repo settings).

---

## PHASE 7: Quality Checklist

Before sharing the deck:

### Content
- [ ] All features described are REAL GroupOS features (verify on groupos.com)
- [ ] No fabricated features or capabilities
- [ ] Organization name is spelled correctly everywhere
- [ ] Membership tiers match the actual organization
- [ ] Pain points are realistic for this org
- [ ] Tools listed in Challenge slide are ones they actually use
- [ ] Terminology matches what the org uses

### Design
- [ ] Cover and CTA are dark slides, everything else is white
- [ ] Yellow accent (#F5C518) used consistently
- [ ] Montserrat font loads correctly
- [ ] All images load (no broken images)
- [ ] Images don't stretch (object-fit:contain)
- [ ] GroupOS watermark visible on all slides (bottom-left)
- [ ] Organization logo on cover and CTA slides
- [ ] Responsive on mobile (test at 375px width)

### Technical
- [ ] Keyboard navigation works (arrows, spacebar)
- [ ] Touch swipe works on mobile
- [ ] Slide counter is accurate
- [ ] Progress bar works
- [ ] No console errors
- [ ] Videos autoplay (muted)
- [ ] GitHub Pages is live and accessible

### Copy
- [ ] No typos
- [ ] Consistent tone (professional but not stiff)
- [ ] Feature descriptions are concise (1-2 lines max per bullet)
- [ ] Headlines are punchy and benefit-focused
- [ ] Subtitles add context without repeating the headline

---

## CRITICAL RULES

1. **NEVER fabricate features** — Only describe what GroupOS actually does. Fetch groupos.com pages to verify.
2. **NEVER use generic copy** — Every deck must feel custom-built for the specific organization.
3. **ALWAYS research first** — Understand the org's structure, programs, and pain points before writing.
4. **Single file only** — All HTML, CSS, JS in `index.html`. No frameworks.
5. **Yellow accent only** — #F5C518 is the GroupOS brand color. Don't change it.
6. **Client brand on cover + CTA** — Their logo appears on first and last slides.
7. **GroupOS watermark on every slide** — Small, subtle, bottom-left.
8. **Verify images load** — Test all CDN URLs before deploying. CDN URLs can change.
9. **Use their language** — Mirror the org's terminology, not generic SaaS speak.
10. **Keep slides scannable** — Big headlines, short bullets, strong images. This is a presentation, not a document.

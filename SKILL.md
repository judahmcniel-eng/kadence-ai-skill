# Kadence WP UI-First Development Expert

## Description

Use this skill when building, editing, planning, or reviewing WordPress sites that use the Kadence Theme, Kadence Blocks, Kadence Elements, Kadence Pro, or Kadence WooCommerce tools.

The core goal is **human-editable WordPress development**. Build in the Kadence visual UI first. Use Kadence Customizer settings, Kadence Blocks, Kadence Elements, Gutenberg controls, and native WordPress settings before reaching for custom PHP, raw HTML, custom CSS, shortcodes, or hardcoded templates.

## First Response Rule

When the user asks for Kadence site work, first identify the most editable native Kadence path.

Good first response pattern:

1. State the Kadence-native approach.
2. Name the exact UI area to use.
3. Explain what should not be hardcoded.
4. Give the build sequence.

Example:

> Build this as a Kadence Row Layout hero, not raw HTML. Set the colors and typography globally first, then build the hero with Kadence Advanced Heading, Text, Image, and Advanced Button blocks. Use block spacing controls for desktop/tablet/mobile instead of custom CSS unless a native setting cannot do it.

## Non-Negotiable Development Order

Follow this order unless the user explicitly asks for custom code:

1. **Customizer first** — global colors, typography, buttons, layout, header, footer, page defaults.
2. **Kadence Blocks second** — Row Layout, Advanced Heading, Advanced Text, Advanced Button, Info Box, Tabs, Accordion, Form, Post Grid/Carousel, Gallery, and other Kadence-native blocks.
3. **Kadence Elements third** — reusable hooked sections, fixed elements, templates, conditional content, banners, custom headers, custom footers, archive/single templates.
4. **Dynamic content fourth** — Kadence dynamic content, ACF fields, featured images, titles, excerpts, post meta, WooCommerce/product fields.
5. **Small CSS only if necessary** — only after confirming no Kadence setting, block control, or Customizer option can do the job.
6. **PHP only as a last resort** — only when native hooks, Elements, Display Rules, or dynamic content cannot achieve the requirement.

## Core Principle

Prefer the approach a non-developer can later edit in WordPress.

If two solutions both work, choose the one with more of the following qualities:

- Editable through the WordPress admin.
- Uses Kadence global settings.
- Uses Kadence block controls instead of code.
- Uses Kadence Elements instead of template files.
- Uses Display Rules instead of conditional PHP.
- Uses reusable sections, patterns, or synced content.
- Keeps styling controlled by global design tokens.

## Hard Bans Unless Explicitly Requested

Do not default to these:

- Editing `header.php`, `footer.php`, `single.php`, `archive.php`, `functions.php`, or child theme templates.
- Building page sections as raw HTML blocks.
- Writing large custom CSS files for layout, spacing, colors, typography, buttons, cards, grids, or backgrounds.
- Using PHP `if/else` visibility logic when Kadence Display Rules can handle it.
- Creating custom shortcodes when a Kadence Block or Element can do the job.
- Installing another page builder just to solve something Kadence can solve.
- Using default core WordPress blocks when a Kadence block gives better responsive and design control.

If custom code is truly required, explain why the Kadence-native path is insufficient and keep the code isolated, minimal, documented, and easy to remove.

## Global Customizer Setup

Before building pages, establish the site-wide Kadence foundation.

### Trigger → Action Rules

User asks for a new site, page system, redesign, landing page set, or style cleanup → define global design first.

User asks for a hero, card grid, sales page, about page, pricing page, or homepage → check whether colors, type, buttons, and content width are already established before building the section.

User asks for “make this consistent” → move repeated local styling into global Customizer settings or reusable Kadence sections.

### Required Global Settings

Set up the Kadence Global Color Palette in four practical groups:

1. **Accents** — primary brand color, secondary accent, CTA color.
2. **Contrast** — main text, muted text, text over dark backgrounds.
3. **Base / Background** — page background, content background, alternate section background.
4. **Notices** — success, warning, error, info.

Set global typography for:

- Body text.
- H1 through H6.
- Buttons.
- Navigation.
- Forms, if relevant.

Set global layout defaults:

- Content width.
- Narrow content width.
- Page container style.
- Sidebar defaults.
- Vertical spacing defaults.
- Button style defaults.
- Form styling defaults.

## Kadence Blocks Build Rules

Use Kadence Blocks as the primary page-building system.

### Row Layout Block

Use the **Kadence Row Layout Block** as the wrapper for major sections.

Use it for:

- Hero sections.
- Two-column layouts.
- Multi-column feature grids.
- Pricing rows.
- Alternating image/text sections.
- Background images, gradients, overlays, sliders, or video backgrounds.
- Section spacing and responsive padding.
- Full-width or constrained layouts.

Do not use raw HTML wrappers for layouts that Row Layout can handle.

### Common Block Choices

Use these defaults:

- Headline → Kadence Advanced Heading.
- Paragraph text → Kadence Advanced Text or Gutenberg paragraph only when no special styling is needed.
- CTA → Kadence Advanced Button.
- Icon/card feature → Kadence Info Box.
- Testimonials → Kadence Testimonials or a Kadence Row Layout/card pattern.
- FAQ → Kadence Accordion.
- Pricing → Kadence Row Layout + Info Box/Button or a native Kadence pricing block if available.
- Contact form → Kadence Form block when the requirements are simple enough.
- Blog/news display → Kadence Posts block, Post Grid, or Query Loop pattern depending on available Kadence tooling.

### Responsive Rule

For every major section, explicitly check desktop, tablet, and mobile controls.

Do not solve mobile layout problems with CSS until you have checked:

- Row Layout column stacking.
- Per-device padding and margin.
- Per-device font sizes.
- Per-device alignment.
- Hide/show settings.
- Container width and content max width.

## Kadence Design Library Rule

When the user needs speed, prototypes, or a standard layout, start with the Kadence Design Library.

Use the Design Library for:

- Wireframes.
- Starter sections.
- Reusable hero layouts.
- Pricing blocks.
- FAQ sections.
- Team sections.
- Feature grids.
- Contact sections.

After importing a pattern, replace local styling with global colors, typography, and button settings where practical.

## Kadence Elements Rules

Use Kadence Elements for modular customization instead of editing theme files.

### Use Elements For

- Announcement bars.
- Sitewide CTAs.
- Custom after-header sections.
- Before-footer opt-ins.
- Custom footers.
- Custom headers.
- Fixed banners.
- Slide-ins or fixed notices.
- Blog post templates.
- Archive templates.
- WooCommerce notices, upsells, or product-page sections.
- Reusable sections inserted by hook.

### Element Types

Choose the element type based on the job:

- **Content Section** — injected content at a hook location.
- **Fixed Element** — sticky/floating/popup-style elements.
- **Template** — replace or control a broader layout/template area.
- **HTML Element** — only when Kadence Blocks cannot handle the markup need.

### Hook Rule

User asks to add content before/after header, before/after content, before/after footer, inside posts, on product pages, or across the whole site → use Kadence Elements with a Hook.

Use visual/predefined hooks first. Use custom hooks only when needed.

When multiple Elements share one hook, assign priority numbers deliberately:

- Lower priority displays earlier.
- Higher priority displays later.
- Leave gaps like 10, 20, 30 so future elements can be inserted cleanly.

## Display Rules and Conditional Logic

Use Kadence Display Rules instead of custom PHP visibility logic.

### Trigger → Action Rules

User asks “show this only on X” → use Display Rules.

User asks “hide this from logged-out users” → use Display Rules by user state or role.

User asks “only on mobile/desktop” → check Kadence responsive visibility settings first.

User asks for seasonal, expiring, campaign, or limited-time content → use Kadence Element visibility/expiration controls where available.

### Conditions to Prefer

Use native Kadence/WordPress conditions for:

- Specific pages.
- Specific posts.
- Post types.
- Categories/tags/taxonomies.
- Archives.
- Search results.
- 404 pages.
- Front page or blog page.
- Logged-in vs. logged-out users.
- User roles.
- Device visibility.
- Time-sensitive campaigns.
- WooCommerce product pages, cart, checkout, account, and shop contexts.

Do not write PHP conditionals unless the visual rule system cannot express the condition.

## Dynamic Content and ACF

Use Kadence Dynamic Content and ACF to create reusable, data-driven templates.

### Use Dynamic Content For

- Post titles.
- Featured images.
- Excerpts.
- Author info.
- Dates.
- Categories/tags.
- Custom fields.
- Product details.
- Testimonials.
- Event information.
- Location details.
- Staff/team profiles.

### ACF Rule

User asks for repeatable content types like properties, rooms, team members, services, events, testimonials, products, locations, or case studies → recommend ACF fields plus Kadence Elements/Templates instead of manually duplicating pages.

### Fallback Rule

Every dynamic field needs fallback thinking.

For each dynamic field, decide:

- What shows if the field is empty?
- Should the block hide if missing?
- Should a default image/text appear?
- Will the layout break if the value is long, short, or missing?

Never leave dynamic templates dependent on perfect data.

## Headers, Footers, and Page Overrides

Use the Kadence Header Builder and Footer Builder for global site structure.

### Header Rules

Use the Header Builder for:

- Logo placement.
- Primary navigation.
- Secondary navigation.
- CTA buttons.
- Search.
- Social icons.
- Account/cart icons.
- Mobile drawer/off-canvas navigation.
- Transparent header.
- Sticky header.

Do not edit `header.php` for header layout changes.

### Footer Rules

Use the Footer Builder for:

- Footer columns.
- Menus.
- Logo.
- Copyright.
- Social links.
- Contact info.
- Newsletter signup.

Do not edit `footer.php` for footer layout changes.

### Landing Page Rules

For unique landing pages:

- Use native Page Settings to disable header and/or footer.
- Use full-width or unboxed content style when needed.
- Remove vertical padding through page settings or Row Layout spacing controls.
- Use Kadence Blocks for the full page structure.

Do not create a custom PHP landing page template unless Kadence page settings cannot achieve the goal.

## WooCommerce Rule

For Kadence WooCommerce work, use WooCommerce settings, Kadence Customizer WooCommerce controls, Kadence Elements, hooks, and Display Rules before custom template overrides.

Use Kadence-native approaches for:

- Product page banners.
- Shop archive notices.
- Cart/checkout trust badges.
- Category-specific CTAs.
- Product-specific upsells.
- Account-page messaging.
- Sale or seasonal notices.

Avoid copying WooCommerce template files into a child theme unless the user specifically needs behavior Kadence cannot control.

## CSS Policy

Custom CSS is allowed only after the Kadence-native path has been checked.

Before writing CSS, verify:

- Is there a Customizer setting?
- Is there a block setting?
- Is there a per-device setting?
- Is there a global style setting?
- Can this be solved with Row Layout, Info Box, Advanced Heading, spacing controls, or color palette tokens?
- Can the section become a reusable Kadence Element instead?

When CSS is necessary:

- Keep selectors specific but not brittle.
- Use clear class names added through block Advanced settings.
- Avoid styling generated Kadence classes directly unless necessary.
- Use CSS variables/global colors where possible.
- Comment why CSS was needed.
- Keep CSS small and scoped.

## PHP Policy

PHP is a last resort.

Before writing PHP, verify:

- Can Kadence Elements place this with a hook?
- Can Display Rules control visibility?
- Can Dynamic Content pull the data?
- Can ACF model the content?
- Can a plugin setting do this safely?
- Can a child theme function be avoided?

When PHP is necessary:

- Put it in a child theme or small site-specific plugin.
- Keep it isolated and documented.
- Avoid editing parent theme files.
- Explain what Kadence could not do natively.
- Include rollback instructions.

## Common Build Recipes

### Hero Section

Use:

1. Row Layout Block.
2. Background image/video/gradient in Row settings.
3. Overlay in Row settings.
4. Advanced Heading.
5. Advanced Text.
6. Advanced Button.
7. Responsive padding and typography controls.

Avoid raw HTML hero markup.

### Announcement Bar

Use:

1. Kadence Element: Content Section.
2. Hook: before header or after header.
3. Display Rules: sitewide or targeted pages.
4. Priority: 10 unless another element needs to appear first.
5. Optional expiration for limited campaigns.

Avoid editing header files.

### Custom Blog Post Template

Use:

1. Kadence Element: Template.
2. Dynamic Content for title, featured image, author, date, category, and content.
3. Display Rules for posts or selected categories.
4. Fallback image/text where needed.

Avoid editing `single.php`.

### Property, Room, Service, or Event Template

Use:

1. Custom post type if needed.
2. ACF fields for structured details.
3. Kadence Element Template for layout.
4. Dynamic Content to map fields into Kadence Blocks.
5. Display Rules for the post type.
6. Fallbacks for missing fields.

Avoid creating one-off duplicated pages.

### Full-Width Landing Page

Use:

1. Native Page Settings.
2. Disable title/header/footer as needed.
3. Set content style to full width or unboxed.
4. Build with Kadence Row Layout sections.
5. Use global colors and typography.

Avoid custom PHP templates.

## Named Failure Modes

Watch for these mistakes and correct them early.

### Failure Mode: Code-First Drift

The build starts with PHP, raw HTML, or CSS before checking Kadence UI controls.

Correction: stop and map the request to Customizer, Kadence Blocks, Kadence Elements, Display Rules, or Dynamic Content first.

### Failure Mode: Local Style Sprawl

Every page section has its own colors, fonts, spacing, and button styling.

Correction: move repeated decisions into global colors, typography, buttons, and reusable Kadence sections.

### Failure Mode: Template File Overreach

The solution edits theme files for headers, footers, single posts, archives, or product pages.

Correction: use Header/Footer Builder, Kadence Elements, Templates, hooks, and Display Rules.

### Failure Mode: Missing Responsive Pass

The desktop layout works but tablet/mobile breaks.

Correction: check Row Layout stacking, per-device padding, font sizes, alignment, and visibility settings.

### Failure Mode: Dynamic Content Fragility

ACF or dynamic fields are inserted with no fallback.

Correction: define fallback content, hide-empty behavior, or safe defaults.

### Failure Mode: Uneditable Client Handoff

The final site technically works but the client cannot safely edit it.

Correction: rebuild the section with Kadence-native blocks/settings or document the small custom code exception.

## Output Style For This Skill

When giving instructions, prefer concrete UI paths and build steps.

Bad:

> Add CSS to make the hero section full width.

Better:

> Select the Row Layout block, set Structure to full width, set Content Max Width to your global content width, then adjust desktop/tablet/mobile padding in the Row Layout spacing controls. Only add CSS if the Row Layout controls cannot produce the needed effect.

When reviewing code or a build plan, explicitly mark each item as:

- **Kadence-native** — recommended.
- **Acceptable small custom code** — only where native controls cannot solve it.
- **Avoid** — code-first, brittle, or hard for humans to edit.

## Final Check Before Delivery

Before calling a Kadence build complete, verify:

- Global colors are used instead of random local colors.
- Global typography is used where possible.
- Row Layout blocks structure the major sections.
- Header/Footer Builder handles header and footer changes.
- Elements handle hooked or reusable sections.
- Display Rules handle visibility.
- Dynamic content has fallbacks.
- Mobile/tablet/desktop views have been checked.
- Any custom CSS/PHP has a clear reason and is minimal.
- A normal WordPress editor can understand and safely edit the result.

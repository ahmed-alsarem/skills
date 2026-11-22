---
name: ahmed-ui-ux-pro-max
description: Design, implement, and improve distinctive, usable web and app interfaces. Combines product-aware visual direction with practical UI/UX patterns, responsive behavior, accessibility, and Arabic RTL support.
metadata:
  short-description: Distinctive end-to-end UI/UX design
---

# Ahmed UI/UX Pro Max

Create interfaces that feel specific to their product and work clearly for their users. Bring together strong visual direction, sound interaction design, and implementation that fits the project. Treat style libraries and patterns as options to evaluate, not recipes to apply blindly.

## Understand the assignment

- Identify the product, audience, platform, user goal, and primary action from the request and project context. Ask only when a missing decision would materially change the result; otherwise make a sensible assumption and state it briefly.
- For an existing project, inspect its framework, current interface, design tokens, components, and conventions before changing direction. Preserve established patterns unless the user requests a redesign.
- Match the approach to the surface: marketing, dashboard, commerce, content, forms, and native app flows have different information and interaction needs.
- Keep scope aligned with the request. A focused fix does not need a full redesign; a new product surface may need a coherent page or flow system.

## Plan a coherent design direction

For a new page or product-wide direction, establish a compact design system before implementation:

- **Visual concept:** one sentence that connects the product and audience to a clear visual idea.
- **Palette:** semantic base, surface, text, accent, and status colors; consider light/dark themes only when needed.
- **Typography:** readable type roles and a clear scale. Check language coverage and available project fonts.
- **Layout:** content hierarchy, grid, density, spacing rhythm, alignment, and responsive behavior.
- **Components and states:** identify the key patterns, actions, and loading, empty, error, success, focus, and disabled states relevant to the flow.
- **Motion:** choose motion only when it clarifies a change or supports the visual concept; respect reduced-motion settings.

When the brief leaves room for style, explore a few meaningfully different directions mentally, then choose one based on product fit. Avoid familiar AI defaults such as identical rounded cards everywhere, decorative gradients, arbitrary badges, generic hero metrics, or repeated animation. These can be right when the brief supports them. If the user specifies a style, follow it.

## Shape a usable experience

- Organize information around what the user is trying to do. Make hierarchy, navigation, and the next action easy to understand.
- Use clear, consistent language. Label actions by their outcome, and keep the same name for the same action throughout a flow.
- Design the relevant interaction states, not just the ideal screenshot. Explain errors plainly, preserve entered data where appropriate, and make empty states point to a useful next step.
- Make controls usable with keyboard, touch, and assistive technology. Provide visible focus, semantic roles and names, adequate contrast, and alternatives to gesture-only actions.
- For data-heavy screens, choose chart and table forms that suit the question users need answered. Label units, time ranges, legends, and important comparisons; do not use color as the sole encoding.
- Use platform conventions when they improve usability, while keeping the product's visual identity consistent.

## Arabic and right-to-left interfaces

- For Arabic-first experiences, set the document or relevant region direction to RTL and use a readable Arabic-capable typeface available to the project.
- Review real Arabic content at desktop and mobile sizes. Check mixed Arabic and Latin text, numbers, dates, punctuation, forms, truncation, and alignment; Latin placeholder text is not a valid RTL layout check.
- Arrange reading and navigation order for RTL. Mirror icons only when their meaning is directional (such as back/forward); keep universal symbols and branded marks in their intended orientation.
- Check bidirectional snippets and user-entered content so their direction does not disrupt surrounding labels or controls.

## Implement with the project

- Use the actual framework, component library, and styling conventions found in the project. Do not introduce dependencies or replace the stack just to match a design preference.
- Reuse or extend design tokens and shared components. Keep component variants and CSS rules understandable, and avoid conflicting selectors or scattered one-off overrides.
- Implement functional interactions when the request calls for a working interface. If producing a visual prototype, make prototype-only behavior clear in the deliverable.
- Keep responsive behavior tied to content and task. Check for overflow, cramped targets, unreadable line lengths, hidden content, and awkward reordering at narrow widths.

## Use design references when they help

If the `ui-ux-pro-max` skill and its local search data are available, use its design-system search for a new product-wide direction, or a focused domain/stack search for a specific concern. Keep queries narrow, verify that results fit the product and platform, then synthesize them with the brief and this skill's visual principles. Skip searches for small, self-contained changes where they add no value. If the skill or its data is unavailable, continue with project context and design judgment; never claim to have searched when you have not.

## Review and refine

- When a browser, simulator, or preview is available, inspect the rendered result at representative desktop and mobile sizes. Review the actual interface, not only the source code.
- Check the most relevant accessibility and interaction concerns for the surface: keyboard focus, control semantics, contrast, text scaling, reduced motion, touch targets, and overlays that obscure content.
- Compare the result to the brief and chosen direction. Fix the biggest usability or visual mismatch first, then remove decoration that does not help.
- Report what was implemented and any meaningful limitations. Do not claim visual or interaction verification that was not performed.

# Visual Preference Script v1

## 1. Base Color System
## 1. Color System

The primary visual identity should be built around the following slate palette:

- 50:  #F8FAFC
- 100: #F1F5F9
- 200: #E2E8F0
- 300: #CBD5E1
- 400: #94A3B8
- 500: #64748B
- 600: #475569
- 700: #334155
- 800: #1E293B
- 900: #0F172A
- 950: #020617

This palette should define the dominant visual appearance of the interface.
Additional colors are allowed whenever they improve usability, hierarchy, branding, or visual balance.
Preferred accent color:
- Purple: #8042F1
The preferred accent color should be considered first, but it is not mandatory. The designer or AI may choose other accent colors when they better fit the context.
Accent colors should complement the primary palette rather than dominate it.

## 2. Shape Language

Sharp visual forms are disallowed unless technically unavoidable.

Avoid:
- sharp corners
- triangular aggressive shapes
- pointed decorative elements
- hard angular UI containers

Preferred:
- rounded geometry
- soft silhouettes
- smooth corner radius
- visually non-aggressive forms

Rule:
Any shape that visually feels pointed, sharp, or spike-like MUST be softened or replaced.

## 3. Typography

Preferred Persian font:
- Vazir

Preferred English fonts:
- Poppins
- Comfortaa

Typography MUST NOT use low variance.

Low variance means:
- same size repeated across most elements
- same weight repeated across most elements
- weak hierarchy between title, subtitle, body, caption, CTA

Typography MUST include visible hierarchy through:
- size difference
- weight difference
- spacing difference
- role-based treatment

## 4. Motion System

Animations MUST include bounce-like behavior.

A motion is valid only if:
1. It moves toward the target.
2. It slightly passes the target.
3. It returns back.
4. It may pass again with lower intensity.
5. It settles at the final target.

Invalid motion:
- linear movement
- instant arrival
- robotic ease-in-out with no overshoot
- static UI with no touch feedback

## 5. Border Policy

Borders are NOT preferred as separators.

Borders are allowed only if:
- they are part of the visual identity
- they improve the composition
- they are not the main separation mechanism

Preferred separation methods:
- spacing
- background contrast
- shadow
- depth
- scale
- opacity

Rule:
If a border exists only to separate two areas, replace it.

## 6. Particle System

Particle elements around the main subject are considered a sign of professional visual design.

Particles MUST be:
- small
- secondary
- not readable as main content
- visually lightweight
- distributed around the subject

Particles MAY be:
- geometric
- abstract
- semi-transparent
- multi-color
- blurred
- irregular

Particles MUST NOT:
- compete with the subject
- look like content
- reduce readability

## 7. Spacing System

Spacing MUST follow a unified vertical rhythm.

Main vertical gaps in a design MUST use a consistent scale.

Invalid:
- random vertical gaps
- visually unrelated section spacing
- inconsistent distance between major blocks

Valid:
- repeated spacing pattern
- section gaps following one scale
- predictable rhythm between major elements

Rule:
Major vertical spacing must be explainable by one spacing system.

## 8. Interaction Feedback

Interactive UI elements MUST provide motion feedback.

Required for:
- button tap
- card tap
- menu open/close
- modal open/close
- page transition
- important state change

Feedback SHOULD include:
- scale
- bounce
- opacity shift
- soft displacement
- delayed settle

Invalid:
- no feedback
- color-only feedback
- instant state change without motion

## 9. Interpretation Lock

These rules MUST be interpreted literally.

Do NOT reinterpret them as:
- generic modern UI
- minimalism
- clean design
- best practice
- Apple-like design
- Material Design
- Tailwind default design

The goal is not universal good design.
The goal is matching this specific visual taste.

## 10. Conflict Resolution

If rules conflict, priority is:

1. Slate-based visual identity
2. Soft non-sharp form language
3. Motion with bounce and overshoot
4. Clear typography hierarchy
5. Unified spacing rhythm
6. Minimal use of borders
7. Particle-supported subject emphasis
8. Touch and interaction feedback

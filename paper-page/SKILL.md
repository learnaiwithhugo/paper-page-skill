---
name: paper-page
description: Design any web page (homepage, landing page, apply page, email, proposal page) in Paper with Claude, section by section. Runs a 5-step flow - context, why/who/sections, lock the copy, build one section at a time in Paper, pick and tweak. Use when the user says "/paper-page", "let's do the [X] page", "design the [X] page in Paper", or wants to work through a page section by section.
argument-hint: [which page, e.g. "homepage for my bakery"]
---

# /paper-page

A method for designing a page in Paper with Claude. The point is to lock the WHY and the
WORDS before anything gets designed, then design one section at a time so every piece gets
the user's eye.

The user may not be technical. Talk in plain English, explain any design word the first time
it comes up, and tell them exactly where to click when they need to do something in Paper.

## The flow

1. Context (where and why)
2. Why this page, who it's for, which sections
3. Lock the copy
4. Build one section at a time in Paper
5. Pick and tweak

Each step ends with the user's yes. Never run two steps in one turn.

---

## Step 1: Context

Read everything before asking anything. Never ask something that's already written down.

- Anything the user has shared or pointed at: a brief, notes, a doc, their current website.
  Treat it as reference, not a bible, unless they say otherwise.
- Paper: `get_guide` first, then `get_basic_info`. Find the approved pieces (usually the
  hero, the top section of the page) and screenshot them. Ignore inspiration clutter and
  rough wireframes unless they point at them.
- If the Paper tools aren't available, stop and help them connect it: open Paper Desktop,
  open a file, click an empty spot on the canvas, then in the MCP panel on the right click
  **Add to Claude** and restart Claude. Guide: https://paper.design/docs/mcp
- Reference websites they name: read them and note the sections in order, the copy, what
  each section is doing, and patterns worth noting.

Then ask only what's missing (what the business does, who visits the page, what they should
do next, any sites they like, any brand colours or fonts).

Report back short: what the page is for, what the reference teaches, anything that clashes
or isn't decided yet. Then move to step 2 in the same message.

## Step 2: Why, who, which sections

- **Who actually lands on this page**, and what's its one job. (Example: a homepage can be a
  trust page for people who Google the business, while the ad goes to a bare landing page.)
- **The section list**, each with one line on WHY it's there.
- Say what was cut or merged and where it went.
- Keep it minimal: "as bare as it can be". Fewer sections beats more.

Wait for the user to cut, merge or reorder.

### If the user asks for a grey wireframe

A wireframe is a checklist, not a design. It shows which sections exist, in what order, and
what each one holds, so the user can see the page at a glance and edit it.

- **Never use the wireframe as a design reference.** Its boxes, grids, card shapes and
  layouts are placeholders. In step 4, every section is designed from its own references
  and the page's look, starting fresh. Never "design the box like the wireframe".
- Keep it plain grey, label every section, and put an orange note on the canvas saying it's
  a placeholder.
- Once the copy locks, update the wireframe so its words and sections match, then leave it.

## Step 3: Lock the copy (before any design)

Write every section's words. For each section give:

- **The copy**, exactly as it would appear.
- **Why** each line is there, in one or two lines.
- **Where it came from**: something the user said, a reference site, or me.

Rules:
- **Never make up a fact.** Anything only the user knows goes in [brackets]. End with a
  short "needed from you" list.
- **Headlines and headings are the user's call.** Give 3 to 6 options with my pick on top
  and the reason. Never pick one and build it.
- Plain English, assume zero context, no em dashes, no jargon without a definition.
- Proof and testimonials: real only on a live site. Made-up ones are fine as a DEMO while
  designing, tagged DEMO on the board so they can't slip onto the live site.

When they lock it, save it to the working file (below) straight away.

## Step 4: Build one section at a time in Paper

Only the section being worked on. Never build the rest of the page ahead of the user.
If a grey wireframe exists, it only tells you what the section holds. Don't look at its
layout when designing.

For each section:
1. **Clarify first** if the section's job is unclear ("is proof testimonials?"). Answer
   with what I think it is, then build.
2. **Find their inspiration** on the canvas (look for labelled references, or ask) and
   screenshot the ones they name. Before building from a reference, write ONE line saying
   what makes it special (e.g. "cards blur and fade out toward the top"). That thing must
   show up in the build. Copying a reference's layout and missing its special detail is the
   most common reason a section gets sent back.
3. **Match the approved sections exactly.** Pull real values with `get_jsx` /
   `get_computed_styles` from the hero (font, ink colour, heading size, tracking, accent,
   radius, section padding). Alternate section backgrounds the same way the page already
   does. If nothing is approved yet, agree a simple look first (2 or 3 colours, 1 or 2 fonts).
4. **Versions: 1 by default.** Do more only when the user asks ("two versions"). Each
   version gets its own artboard.
5. **Name artboards** `[Section] · [A/B] · [what's different]`, e.g. "Proof · B · Sliding
   rows". Main-column picks go in page order; alternates sit to the left.
6. **Animation can't be shown in Paper.** Draw the most telling frame (mid-slide, answered
   state) and add a small orange note tag on the board describing the motion.
7. **Screenshot and check before showing them**: spacing, contrast, alignment, nothing
   clipped, headline line breaks clean, no duplicate cards next to each other, logos and
   images actually loading. Fix it first. Call `finish_working_on_nodes` when done.

Then tell them in a few bullets what's on each board and where it sits on the canvas, plus
anything still in [brackets].

## Step 5: Pick and tweak

They pick, tweak, or send it back. Apply exactly what they say, nothing extra. Copy changes
go into the working file. Then on to the next section.

---

## The working file

Keep `page-plan-[page].md` next to the page work (ask once where if it's not obvious). If
you can't save files, keep it as a summary in the chat instead. It holds:
- who the page is for and its one job
- the section list and the locked copy, with the whys
- "needed from you"
- which Paper artboard is which, and which version they picked

Update it whenever something locks. It means a fresh chat can carry on straight away. When
starting, check whether one already exists and pick up from it.

## Done

Stop when every section is locked in Paper. Building the real page in code is a separate
job that waits for the user to say "build it".

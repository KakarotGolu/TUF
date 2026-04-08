An interactive wall calendar built with Next.js 14 and CSS Modules — zero UI library dependencies. Inspired by a physical spiral-bound wall calendar with a full-bleed hero photo, chevron wave design, date range selection, and an integrated notes panel.

Features

Wall Calendar Aesthetic — portrait layout with full-bleed monthly hero image, SVG chevron wave cutting across the photo, and a blue angled month/year label block
Date Range Selector — click a single day or click-and-drag across multiple days to select a range; clear visual states for start, end, and in-between days
Integrated Notes — write notes tied to a selected date range or the whole month; saved notes persist via localStorage and display inline below the grid
Holiday Markers — dot indicators on public holidays from a static JSON list
Responsive Design — side-by-side desktop layout collapses to a stacked vertical layout on mobile
Month Navigation — prev/next arrows with a smooth page-flip CSS animation


Tech Stack

Next.js 14 (App Router)
CSS Modules — scoped styles, no Tailwind or UI framework
Custom React Hooks — useCalendarState.js manages all state
localStorage — client-side note persistence, no backend


Getting Started
bash# 1. Clone the repo
cd wall-calendar

# 2. Install dependencies
npm install

# 3. Run the dev server
npm run dev
Open http://localhost:3000 in your browser.

Project Structure
/components/WallCalendar/
  WallCalendar.jsx       # Parent shell component
  HeroSection.jsx        # Hero image + SVG chevron + month/year label
  CalendarGrid.jsx       # Days grid with drag-to-select range logic
  NotesPanel.jsx         # Lined textarea + saved notes list
  useCalendarState.js    # Custom hook — month, range, notes state
  calendar.module.css    # All component styles

/data/
  holidays.json          # Static public holidays list

/pages/
  index.js               # Demo page

Design Decisions

SVG chevron — the wave shape cutting across the hero image is an inline <svg> with a <polygon> — no image editing required, scales perfectly at any size
Mon-start weeks — matches the reference design (European-style Mon–Sun grid)
Drag-to-select — implemented via mousedown / mouseenter / mouseup events with a global mouseup listener to handle releasing outside the grid
No backend — the brief specified frontend only; localStorage handles note persistence cleanly


# A Scream in the Night - DM Companion App

## Project Overview
A single-file React app (`index.html`) that serves as a DM companion for running the D&D Adventurers League module **CORE 1-1 "A Scream in the Night"** by M. Sean Molley. The user is a **new DM** and this app is designed to help them flow through the session confidently.

## Party
- 6 Level 1 players: Paladin, Monk, Ranger, Warlock, Sorcerer, Barbarian
- Party strength: **Strong** (use Strong party encounter adjustments throughout)

## Architecture
- **Single file**: Everything is in `index.html` - React 18, Babel, and Tailwind CSS loaded via CDN
- **No build step**: Open in browser or host on GitHub Pages
- **The `src/` directory is unused boilerplate** from the original Vite scaffold - ignore it entirely
- **GitHub Pages**: Hosted at `https://baronza.github.io/scream-in-the-night/`

## Key Technical Details
- React 18 via CDN with Babel for JSX transpilation in-browser
- Tailwind CSS via CDN for styling
- Google Fonts: Cinzel (display) and Crimson Text (body)
- All state via React `useState` hooks
- **localStorage persistence**: Slide position, HP tracking, and story notes auto-save under key `scream-dm-companion`
- "New Session" button in header resets all saved state

## App Structure (inside index.html)
- **CAMPAIGN_DATA** object holds all 13 slides with rich content
- **Section** component: Collapsible panels color-coded by type (amber=read-aloud, green=roleplay, blue=mechanics, purple=DM tips, slate=FAQ)
- **NPCCard** component: NPC roleplay guides with sub-sections for attitudes, player Q&A, and spoiler guards
- **Combat tracker**: HP tracking with +/-1/5 buttons, persists across slides
- **Timeline sidebar**: Shows the murder schedule (8/9/10 bells)
- **Story Notes panel**: Track Boltac/Zellani saved/died, add timestamped notes

## Content Per Slide
Each slide can have these optional fields:
- `readAloud` - Boxed text to read to players (from the PDF module)
- `description` - DM-facing narrative context
- `roleplay` - NPC guides with: name, race, appearance, personality, quote, attitudes, playerQuestions, doNotReveal
- `mechanics` - DCs, rules, skill checks, procedures
- `dmTips` - Advice for running the scene
- `faq` - Common player questions with answers

## The 13 Slides
1. Session Start (intro) - Setup, objectives, C1e7i5 backstory
2. Opening - Winking Narwhal (narrative) - Tavern exit, brawl distraction, drunken sailors
3. Enc 1: Caltrops Fight (combat) - 5 swarms, murder scene, 8 bells
4. Enc 2: First Murder (investigation) - Eledstra arrives, puzzle 1, deputization
5. Travel to Marketplace (narrative) - Search mechanics, marketplace vendors
6. Enc 3: Save Boltac (combat) - 8 Gondsmen + C1e7i5 sniper, Boltac & Ellywicket NPCs
7. Puzzle 2: The Grid (investigation) - 3x3 grid puzzle solution
8. Travel to Temple (narrative) - Temple approach options
9. Convince Zellani (roleplay) - Zellani NPC, persuasion DCs
10. Enc 4: Temple Chaos (combat) - Chaos creatures + devils, saving Zellani mechanic
11. Enc 5: Rooftop Chase (skill-challenge) - 8 planar obstacles, abstract zones
12. Lighthouse Finale (narrative) - Modron reveal, portal to Mechanus
13. Rewards & Conclusion - XP, gold, story awards, adamantine forging table

## Source PDF
The adventure PDF is: `CORE_1-1_A_Scream_in_the_Night1-4.pdf` (42 pages)
- No Python on Windows machines used for this project
- PDF text extraction works via `npx pdf-parse text <file>`

## NPCs with Full Roleplay Guides
- **C1e7i5** ("Cletis") - Rogue quadrone modron, the villain (DM reference only)
- **Sergeant Eledstra** - City Watch officer, primary quest-giver ally
- **Boltac Thurdingard** - Dwarven adamantine blacksmith, murder target #2
- **Ellywicket "Elly" Klemwocket** - Gnome priestess of Gond, Gondsmen owner
- **Zellani** - Half-elf priestess of Loviatar, murder target #3
- **Drunken Sailors** - Comic relief minor NPCs
- **Marketplace Vendors** - Info source for finding Boltac

# Pi Visual Builder — PiRC4: Visual App Builder Standard

> **Advanced Mode for Pi App Studio** — Visual drag-and-drop builder for React/TypeScript web apps that run natively inside Pi Browser.

## The Problem

Pi App Studio (launched June 2025) enables no-code app creation via AI prompts and templates. However, it has limitations:

| Limitation | Impact |
|-----------|--------|
| **AI decides the layout** | Developers can't fine-tune UI pixel-by-pixel |
| **No visual logic editor** | Complex app behavior requires prompt engineering, not direct control |
| **No code access** | Can't view or edit the generated code |
| **Template-only** | Can't build custom components or reuse logic patterns |
| **Beginner ceiling** | Advanced developers hit a wall quickly |

## The Solution: Pi Visual Builder

A **visual app development environment** that complements Pi App Studio with an Advanced Mode:

### 1. Visual UI Designer (Drag-and-Drop)
- Component palette: buttons, lists, images, maps, charts, webviews
- Property inspector: size, color, font, margin, padding, animations
- Responsive preview: phone, tablet, Pi Browser
- Custom themes with Pi Design System tokens

### 2. Logic Blocks (Visual Programming)
- Event-driven blocks: `onTap`, `onLoad`, `onSwipe`, `onTimer`
- Logic blocks: `if/else`, `loop`, `switch`, `try/catch`
- Data blocks: variables, lists, maps, API calls
- Pi-specific blocks: `sendPi`, `verifyPioneer`, `getProfile`, `createEscrow`
- Custom block creation with reusable logic

### 3. Code View & Edit
- **React/TypeScript** code generated from visual design
- **HTML/CSS** mode for direct markup editing
- Switch between Visual ↔ Code view at any time
- All apps run as **web apps inside Pi Browser** (no external deployment)
- Pi SDK JavaScript library auto-imported

### 4. Component Marketplace
- Publish custom components
- Import community components
- Pi-verified component badges
- Monetization with Pi payments

## Architecture

```
┌─────────────────────────────────────────┐
│           Pi Visual Builder             │
├──────────┬──────────┬───────────────────┤
│  UI      │  Logic   │  Code             │
│ Designer │  Blocks  │  Generator        │
│          │          │                   │
│ ┌──────┐ │ ┌──────┐ │ ┌───────────────┐ │
│ │Canvas│ │ │Event │ │ │ React/TS Code  │ │
│ │      │ │ │Blocks│ │ │ HTML/CSS View  │ │
│ │Props │ │ │Logic │ │ │ Pi Browser Pkg │ │
│ │Panel │ │ │Blocks│ │ └───────────────┘ │
│ └──────┘ │ └──────┘ │                   │
├──────────┴──────────┴───────────────────┤
│         Pi SDK Integration              │
│  (Auth, Payments, Escrow, Reputation)   │
├─────────────────────────────────────────┤
│         Component Marketplace           │
└─────────────────────────────────────────┘
```

## Pi-Specific Blocks

| Block | Category | Description |
|-------|----------|-------------|
| `pioneer.login()` | Auth | Pi authentication flow |
| `pioneer.getProfile()` | Auth | Get Pioneer profile data |
| `pi.send(amount, recipient)` | Payment | Send Pi payment |
| `pi.createEscrow(buyer, seller, amount)` | Commerce | Create PiDCTP escrow |
| `pi.verifyMerchant(address)` | Commerce | Check merchant status |
| `pi.getReputation(address)` | Trust | Get reputation score |
| `pi.openDispute(escrowId)` | Trust | Open dispute |
| `pi.earnLoyalty(pioneer, action)` | Rewards | Award loyalty points |
| `pi.subscribe(planId)` | Subscription | PiRC2 subscription |

## Component System

### Built-in Components
- **Layout**: Column, Row, Stack, Grid, ScrollView, TabView
- **Display**: Text, Image, Icon, Badge, Avatar, Card, Chart
- **Input**: TextField, TextArea, Switch, Slider, DatePicker, Picker
- **Action**: Button, IconButton, FloatingActionButton, Chip
- **Navigation**: NavBar, Drawer, BottomSheet, PageView
- **Pi-specific**: PioneerCard, PiPayButton, EscrowStatus, ReputationBadge, MerchantProfile

### Custom Components
```json
{
  "name": "ProductCard",
  "version": "1.0.0",
  "author": "pioneer_address",
  "props": {
    "title": "String",
    "price": "Number",
    "image": "Uri",
    "onBuy": "Event"
  },
  "template": "ui_layout.json",
  "logic": "logic_blocks.json",
  "exports": ["react", "html"]
}
```

## File Format

### Project Structure
```
my-pi-app/
├── manifest.json          # App metadata & permissions
├── theme.json             # Pi Design System tokens
├── screens/
│   ├── home.ui.json       # Visual layout
│   ├── home.logic.json    # Logic blocks
│   └── product.ui.json
├── components/
│   └── ProductCard.json   # Custom component
├── assets/
│   ├── images/
│   └── fonts/
└── dist/
    └── pibrowser/         # Pi Browser web app package
```

### UI Layout Format (`.ui.json`)
```json
{
  "type": "Screen",
  "id": "home",
  "children": [
    {
      "type": "Column",
      "children": [
        { "type": "Text", "props": { "value": "Welcome, Pioneer!", "style": "headline" } },
        { "type": "PiPayButton", "props": { "amount": 10, "recipient": "${seller}" } }
      ]
    }
  ]
}
```

### Logic Block Format (`.logic.json`)
```json
{
  "events": [
    {
      "trigger": "onTap",
      "target": "PiPayButton",
      "actions": [
        { "type": "call", "method": "pi.createEscrow", "args": { "buyer": "${pioneer}", "seller": "${seller}", "amount": 10 } },
        { "type": "navigate", "screen": "escrow_status" }
      ]
    }
  ]
}
```

## Integration with PiDCTP (PiRC3)

Pi Visual Builder provides **visual blocks** for all PiDCTP modules:

| PiDCTP Module | Visual Blocks Available |
|---------------|------------------------|
| Escrow | Create, Fund, Confirm, Cancel, Milestone, Group |
| Reputation | View Score, Award Badge, Create Attestation |
| Dispute | Open, Submit Evidence, Vote, View Ruling |
| Merchant | Apply, Verify, View Profile |
| Loyalty | Earn Points, Redeem, View Tier |

This means **any Pioneer** can build a commerce app with escrow protection and reputation — without writing a single line of code.

## Roadmap

| Phase | Feature | Status |
|-------|---------|--------|
| **v0.1** | UI Designer + basic components | Proposed |
| **v0.2** | Logic blocks + event system | Proposed |
| **v0.3** | Pi SDK blocks + PiDCTP integration | Proposed |
| **v0.4** | Code view (React/TS + HTML/CSS) | Proposed |
| **v0.5** | Component marketplace | Proposed |
| **v1.0** | Full integration with Pi App Studio as Advanced Mode | Proposed |

## Technical Stack

- **Editor**: React + TypeScript (runs inside Pi Browser)
- **App Framework**: React 18 + TypeScript (generated apps)
- **Styling**: CSS Modules + Pi Design System tokens
- **Code Generation**: AST-based React/TS template engine
- **HTML Mode**: Direct HTML/CSS editing for simple pages
- **Runtime**: Pi Browser (all apps are web apps)
- **Pi SDK**: `@pi/sdk` JavaScript library (auth, payments, escrow, reputation)
- **Build**: Vite (fast HMR inside Pi Browser)
- **Storage**: Pi Cloud (project hosting within ecosystem)

## Quick Start (Concept)

```
1. Open Pi Visual Builder in Pi Browser
2. Drag components onto canvas
3. Connect logic blocks visually
4. Add Pi-specific blocks (payments, escrow, reputation)
5. Preview in device simulator
6. Switch to Code view to edit React/TS or HTML directly
7. Build as Pi Browser web app
8. Publish to Pi App Studio ecosystem
```

## License

MIT License

## Links

- **PiRC3 (PiDCTP)**: https://github.com/PiNetwork/PiRC/pull/378
- **Pi App Studio**: Available in Pi Browser
- **Pi Developer Guide**: https://pi-apps.github.io/community-developer-guide/

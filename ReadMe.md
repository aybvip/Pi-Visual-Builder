# Pi Visual Builder — PiRC4: The Ultimate No-Code Ecosystem for Pi

> **Bubble.io Ecosystem Meets Pi Network AI** — A full-scale visual development platform with a native AI Agent. Build complex, database-driven web apps with visual workflows, all running natively inside the Pi Browser.

## 🚀 The Vision: Beyond AI Generation

While **Pi App Studio** (launched June 2025) pioneered AI-based app creation, **Pi Visual Builder** introduces the **"Visual & AI Hybrid"** era. It provides a professional-grade development environment that combines the ease of AI with the power of a full no-code engine like Bubble.io.

## 🤖 Integrated Pi AI Agent
Following the latest industry standards (as seen in the provided reference images), Pi Visual Builder features a **context-aware AI Agent**:

- **Natural Language Development**: "Build a form so users can apply to jobs" → AI generates the UI, database schema, and workflows simultaneously.
- **Visual Reworking**: "Make the header modern and add a gradient background" → AI updates the Design tab in real-time.
- **Workflow Automation**: "When the user clicks apply, create a record and notify the employer" → AI builds the logic chain in the Workflow tab.
- **Real-time Debugging**: AI identifies and fixes issues in your logic or responsive design.

## 🏛️ The Five Tabs of Power

### 1. Design Tab (Visual UI)
- **Pixel-Perfect Canvas**: Drag-and-drop elements with absolute or flexbox positioning.
- **Elements Tree**: Comprehensive list of components (Basic, Visual, Layouts, Pi-Native).
- **Responsive Engine**: Visual breakpoints to ensure your app looks great on every Pioneer's device.
- **Property Editor**: Full control over fonts, colors, animations, and conditional states.

### 2. Workflow Tab (Visual Logic)
- **Bubble-style Event Loops**: "When [Trigger] → Do [Action 1] → Do [Action 2]..."
- **Complex Branching**: Visual if/else paths and custom reusable workflows.
- **Pi-Native Triggers**: `onPaymentSuccess`, `onAuth`, `onDisputeRuling`, `onMilestoneReached`.
- **Background Workflows**: Scheduled tasks and API-triggered logic.

### 3. Data Tab (Built-in Database)
- **Visual Schema Builder**: Define Data Types (User, Product, Job, Application).
- **Relational Data**: One-to-many and many-to-many linking (e.g., Job linked to Employer).
- **Privacy Rules**: Field-level security (e.g., "Only the applicant can see their social security number").
- **PiDCTP Sync**: On-chain reputation and escrow states are auto-mapped to database records.

### 4. API Tab (Connector)
- **Zero-Code API Connector**: Connect to any external REST or GraphQL service.
- **Native Pi SDK integration**: Visual blocks for all Pi Network core functions.
- **Webhooks**: Let external systems trigger workflows in your Pi app.

### 5. Plugins Tab (Extensibility)
- **Marketplace**: Install community-built components and logic modules.
- **Monetization**: Authors earn Pi for their premium plugins.

## 🏗️ Technical Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                   PI VISUAL BUILDER (VB)                    │
├─────────────────────────────────────────────────────────────┤
│ 🤖 PI AI AGENT (Orchestrator & Copilot)                     │
├──────────┬───────────┬───────────┬───────────┬──────────────┤
│  DESIGN  │ WORKFLOW  │   DATA    │    API    │   PLUGINS    │
│  CANVAS  │  ENGINE   │  MANAGER  │ CONNECTOR │  MARKETPLACE │
└──────────┴─────┬─────┴─────┬─────┴─────┬─────┴──────┬───────┘
                 │           │           │            │
      ┌──────────▼───────────▼───────────▼────────────▼───┐
      │               PI SDK & PiDCTP LAYER               │
      │   (Auth, Payments, Escrow, Reputation, Dispute)   │
      └──────────────────────────┬────────────────────────┘
                                 │
                 ┌───────────────▼───────────────┐
                 │       PI BROWSER RUNTIME      │
                 │ (React/TS + HTML/CSS Web App) │
                 └───────────────────────────────┘
```

## 🔗 Deep PiDCTP (PiRC3) Integration

Pi Visual Builder is built to be the "Frontend" for the **PiRC3 protocol**:

| Visual Workflow Action | Underlying PiDCTP Logic |
|-------------------------|--------------------------|
| `When "Apply" clicked` | Create Job Application record in Data Tab |
| `Do "Secure Payment"` | **Pi.Escrow.create()** (Milestone-based) |
| `Verify Applicant` | **Pi.Reputation.getEffectiveScore()** |
| `Award Work Badge` | **Pi.Reputation.awardBadge(JobVeteran)** |
| `Open Dispute` | **Pi.Dispute.open()** with evidence upload |

## 📅 Roadmap

- **Phase 1: Visual Foundation** (UI Canvas + Basic Workflows).
- **Phase 2: Data Intelligence** (Relational Database + Privacy Rules).
- **Phase 3: AI Integration** (Pi AI Agent for natural language app building).
- **Phase 4: Global Ecosystem** (Plugin Marketplace + Pi App Studio Sync).

## 📄 License
MIT License - 2026 Pi Network Community Contribution.

---

### Links
- **PiRC3 (PiDCTP)**: [PR #378](https://github.com/PiNetwork/PiRC/pull/378)
- **Community Discussion**: [Issue #381](https://github.com/PiNetwork/PiRC/issues/381)

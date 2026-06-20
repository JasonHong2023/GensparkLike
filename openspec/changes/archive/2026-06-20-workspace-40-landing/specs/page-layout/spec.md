## ADDED Requirements

### Requirement: Workspace 4.0 landing page layout

The system SHALL serve a `/workspace/` page that visually mirrors the genspark.ai/zh-tw "Genspark AI 工作空間 4.0" landing page structure, including Navbar, Hero section with pricing cards, Products section, Tools directory, and Footer with language selector.

#### Scenario: Navigate to workspace from homepage
- **WHEN** user clicks "開始探索 / Start Exploring" button on the homepage
- **THEN** browser navigates to `/workspace/`
- **AND** the workspace page renders with correct layout

#### Scenario: Workspace page structure
- **WHEN** user opens `/workspace/`
- **THEN** the page SHALL display a Navbar with items: 首頁, 技能, 工作流程, 雲端硬碟, 更多
- **AND** the Hero section SHALL display "GensparkLike AI 工作空間 4.0" badge
- **AND** the Hero section SHALL display tagline about dashboards/CRM/systems
- **AND** the Hero section SHALL display three pricing cards (個人, Team, 企業)
- **AND** the Products section SHALL display 4 product cards (Claw, Speakly, GenClipboard, GenTerminal)
- **AND** the Tools section SHALL display 4 category columns of tools
- **AND** the Footer SHALL include product links, tools, about, downloads, social icons, and language selector

#### Scenario: All interactive elements are placeholders
- **WHEN** user clicks any Navbar link (except 首頁), product card, tool link, footer link, CTA button, or social icon
- **THEN** no navigation or action occurs (href is `#`)
- **AND** the page remains unchanged

### Requirement: Homepage navbar restructured

The homepage `index.html` SHALL update its navbar to match the genspark.ai navigation structure.

#### Scenario: Homepage navbar shows genspark-style items
- **WHEN** user loads `index.html`
- **THEN** the Navbar SHALL display: Logo "GensparkLike" | 首頁 | 技能 | 工作流程 | 雲端硬碟 | 更多
- **AND** the "開始探索 / Start Exploring" button SHALL link to `workspace/`

# ⚡ VOLT — Valero Operational & Logistics Intelligence Terminal
An interactive financial modeling, geospatial logistics, and supply chain analytics terminal that bridges SEC audited disclosures (Valero Energy Corp Form 10-K) with physical downstream refining and distribution reality.

# Table of Contents
1. Project Overview
2. Problem Statement
3. Project Objectives
4. Intended Users & Practical Use Cases
5. Technology Stack
6. Application Architecture & Directory Structure
7. Key Features & Implementation Status
8. Financial & Operational Calculations
9. Data Sourcing & Verification Methodology
10. Key Financial & Operational Metrics
11. Application Workflow
12. Installation Instructions
13. Instructions for Running Locally
14. Screenshots & Visual Placeholders
15. Testing & Validation Status
16. Known Limitations & Assumptions
17. Future Development Roadmap
18. License Information
19. Project Status

# 1. Project Overview
VOLT (Valero Operational & Logistics Intelligence Terminal) is an analytical platform built using Python and Streamlit. The application translates corporate financial filings—specifically Valero Energy Corporation's Form 10-K disclosures (Item 1 throughput capacities, Note 4 joint venture equity disclosures, Note 19 purchase/transportation commitments, and Note 21 revenue disaggregations)—into dynamic mathematical engines and interactive visual interfaces.
By mapping raw crude sourcing, regional conversion mechanics, logistics tariffs, and working capital inventory drag, VOLT enables quantitative analysis of downstream energy operations and refining asset valuations.

# 2. Problem Statement
Evaluating downstream petroleum refining equity and credit risk presents significant analytical hurdles:Disconnection Between SEC Disclosures and Physical Operations: Financial statements report aggregate figures (e.g., total segment revenues or purchase commitments) without showing how physical commodity flows across regional nodes generate those financial results.
Complex Feedstock & Conversion Economics: Refiners operate across varying regional crude slates (light sweet vs. heavy sour discounts) and secondary conversion complexities (Nelson Complexity Index), making generic crack spread metrics inaccurate.
Opaque Working Capital Drag & Inventory Risk: Capital tied up in multi-stage transit and buffer storage creates carrying costs under fluctuating WACC, while drawdowns below historical LIFO inventory pools trigger unmodeled tax liabilities and artificial margin expansions.
Geospatial & Disruption Vulnerabilities: Static financial models fail to quantify the immediate margin impact of logistical bottlenecks, pipeline tariff shocks, or regional refinery outages (e.g., Gulf Coast hurricane curtailments).

# 3. Project Objectives
Physicalize Financial Disclosures: Convert static SEC footnotes and Item 1 asset tables into interactive, glass-box simulation models with direct audit verification traces.
Model End-to-End Downstream Lifecycle: Map the supply chain across four operational stages: (1) Sourcing & Procurement, (2) Refining & Processing, (3) Logistics & Transport, and (4) Distribution & Sale.
Quantify Working Capital Velocity: Compute real-time capital drag ($C_{\text{carry}}$) across cash-to-cash lead times and monitor LIFO base layer liquidation triggers.Establish a Benchmarking Architecture: Anchor the terminal to Valero Energy (VLO) as an audited baseline preset while providing a fully customizable framework to analyze competing refiners.

# 4. Intended Users & Practical Use Cases
Equity Research & Buy-Side Energy Analysts: Model regional refining segment operating income based on spot crack spreads, heavy crude differentials (WCS/Maya), and scheduled turnaround outages.
Credit Analysts & Risk Officers: Stress-test take-or-pay pipeline and marine charter commitments ($890M+ annual MVOs) against tariff inflation and operational downtime.
Supply Chain & Logistics Strategists: Simulate freight rate shocks, transit velocity variations, and geospatial asset disruptions across global export corridors.Corporate Finance & Accounting Professionals: Evaluate LIFO inventory layer aging, capital carrying drag under changing WACC, and Section 45Z / RINs regulatory offset impacts.

# 5. Technology StackComponent
Technology / LibraryDescriptionRuntime & UIPython 3.10+, Streamlit v1.30+Core execution environment and interactive dashboard framework.Data AnalyticsPandas, NumPyVectorized mathematical operations and tabular transformations.Geospatial EnginePyDeck (Deck.gl wrapper)3D arc layers, point-cloud elevation nodes, and interactive map projections.Flow VisualizationsPlotly (graph_objects, express)Interactive multi-stage Sankey diagrams and waterfall charts.Math FormattingMathJax / LaTeXFormatted financial and operational equations.

# 6. Application Architecture & Directory StructureVOLT-Terminal/
├── app.py              # Single-File Streamlit Master Application & Module Dispatcher
├── requirements.txt    # Python runtime package dependencies
├── README.md           # Master System Documentation & Architectural Guide
└── .gitignore          # Version control exclusion rules

# 7. Key Features & Implementation Status
Feature / ModuleStatusDescriptionPhase 1: Feedstock Sourcing🟢 ImplementedRegional crude slate registry, landed cost simulator (WCS/Maya discounts), DGD renewable feedstocks, and SEC Note 19 obligations.Phase 2: Refining Nodes🟢 Implemented14-refinery capacity footprint (3.2M BPCD), regional weighted NCI indexer, product yield transformation, and turnaround schedule engine.Phase 3: Logistics & Channels🟢 ImplementedLogistics lease commitments registry, freight rate shock simulator, export destination mapping, and Note 21 segment revenue breakdown.Phase 4: Unified Terminal🟢 ImplementedConsolidated PyDeck supply map, throughput vs. crack spread margin capture dashboard, and Plotly Sankey volumetric flow diagram.Phase 5: Geospatial Command🟢 ImplementedGlobal/Regional PyDeck viewports, 3D elevation flows, and hurricane outage stress-testing scenario toggle.Cost & Velocity Architecture🟢 Implemented4-Stage operational hub featuring Valero audited baseline presets vs. custom company parameter override toggles.Margin Spread Engine🟢 ImplementedInteractive Node-by-Node margin waterfall calculator isolating landed cost, NCI uplift, OpEx, and compliance drags.Supply Chain Velocity🟢 Implemented5-stage cash-to-cash lead time calculator (Inbound Transit, Buffer, Processing, DSI, DSO) with capital drag calculations.LIFO Staging Matrix🟢 ImplementedMatrix detailing cost drivers, velocity bounds, and LIFO accounting impacts across 4 lifecycle stages with holding time controls.LIFO Liquidation Monitor🟢 ImplementedAutomated risk engine detecting inventory volume drawdowns below historical base pools and calculating artificial tax/margin spikes.Live SEC EDGAR API Scraping🟡 SimulatedSEC citations and verbatim snippets are hardcoded from verified 2025 10-K filings; live automated scraper pipeline is staged for future deployment.Multi-Company Benchmark Engine🔵 PlannedAutomated side-by-side benchmarking database for Marathon Petroleum (MPC), Phillips 66 (PSX), and PBF Energy.Legend: 🟢 Implemented | 🟡 Partially Implemented / Simulated | 🔵 Planned8. Financial & Operational CalculationsA. Landed Feedstock Cost ($C_{\text{landed}}$)$$C_{\text{landed, WCS}} = (P_{\text{WTI}} - \Delta_{\text{WCS}}) + T_{\text{Enbridge/TMX}}$$$$C_{\text{landed, Maya}} = (P_{\text{WTI}} - \Delta_{\text{Maya}}) + T_{\text{Waterborne}} + F_{\text{demurrage}}$$$$\bar{C}_{\text{landed}} = \sum_{i} (C_{\text{landed, } i} \times w_i)$$Units: USD per barrel ($\$/\text{bbl}$)Assumptions: Default baseline weights ($w_i$): Permian WTI ($40\%$), WCS ($35\%$), Maya ($25\%$).Limitations: Assumes pipeline tariffs remain linear regardless of batch volumes.B. NCI Complexity Uplift & Gross Refining Margin ($GRM$)$$U_{\text{NCI}} = (\text{NCI} - 8.0) \times 0.35$$$$V_{\text{adjusted product}} = V_{\text{basket}} + U_{\text{NCI}}$$$$GRM = V_{\text{adjusted product}} - \bar{C}_{\text{landed}}$$Units: USD per barrel ($\$/\text{bbl}$)Assumptions: Baseline Nelson Complexity Index benchmarked to Valero fleet average ($12.7$). Bonus coefficient fixed at $\$0.35/\text{bbl}$ per NCI point above $8.0$.C. Daily Capital Carrying Drag ($C_{\text{carry}}$)$$C_{\text{carry}} = \left(\bar{C}_{\text{landed}} \times \frac{\text{WACC}}{365}\right) + F_{\text{storage}}$$Units: USD per barrel per day ($\$/\text{bbl/day}$)Assumptions: Valero baseline WACC set to $8.5\%$; default daily storage fee set to $\$0.08/\text{bbl/day}$.D. LIFO Layer Liquidation Margin Expansion ($\Delta M_{\text{LIFO}}$)$$\text{If } V_{\text{current}} < V_{\text{base pool}}: \quad \Delta M_{\text{LIFO}} = (P_{\text{replacement}} - P_{\text{historical base}}) \times (V_{\text{base pool}} - V_{\text{current}})$$Units: Millions of USD ($\$M$)Assumptions: Base pool baseline anchored to audited historical layer volume ($48.0\text{M bbls}$) and cost ($\$42.00/\text{bbl}$).Limitations: Does not incorporate federal/state income tax rate brackets in calculating post-tax net income drag.9. Data Sourcing & Verification MethodologyAll baseline parameters, asset capacities, contract obligations, and financial segment data are extracted from public SEC disclosures of Valero Energy Corporation (SEC CIK: 0001035002):Item 1 (Business — Refining Operations): 14 petroleum refineries, nameplate throughput capacity ($3.2\text{M BPCD}$), crude slate composition.Item 8, Note 1 (Accounting Policies): Deferred turnaround maintenance policy and amortization methodology.Item 8, Note 4 (Joint Ventures): Equity investment in Diamond Green Diesel (DGD) and nameplate renewable production ($1.2\text{B gal/yr}$).Item 8, Note 19 (Commitments & Contingencies): Take-or-pay pipeline transportation and marine throughput obligations ($\$890\text{M}$ for 2026).Item 8, Note 21 (Segment Disaggregation): External revenue disaggregation across Refined Products ($\$132.4\text{B}$), Renewable Diesel ($\$5.2\text{B}$), and Ethanol ($\$4.8\text{B}$).10. Key Financial & Operational MetricsNelson Complexity Index (NCI): A metric quantifying the secondary conversion capacity of a petroleum refinery relative to primary crude distillation. Higher NCI enables heavy, high-sulfur crude processing into high-value light products.3-2-1 Crack Spread: A gross margin benchmark representing the yield from three barrels of crude oil into two barrels of gasoline and one barrel of distillate (diesel/jet fuel).Days Sales of Inventory (DSI): The average temporal duration raw feedstock and finished products are held in network tankage before final sale.Take-or-Pay Minimum Volume Obligation (MVO): Unconditional contractual commitments requiring minimum payments to pipeline and terminal operators regardless of actual throughput volume utilized.Renewable Identification Numbers (RINs): Tradable regulatory credits generated under the EPA Renewable Fuel Standard (RFS) used to quantify refiners' blending compliance obligations.11. Application Workflow┌────────────────────────────────────────────────────────────────────────┐
│                        VOLT TERMINAL SIDEBAR                           │
│  Select Module Focus (Overview, Phases 1-5, Cost Hub, Formula Engines) │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                    HEADER AUDIT BAR & SEC CITATION                     │
│    Inspect SEC Filing Source, Accession #, Snippet, & Execution Path   │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                     INTERACTIVE CONTROL DASHBOARD                      │
│   • Toggle "Valero Audited Baseline Presets" vs. Custom Parameters     │
│   • Adjust Benchmark Crudes (WTI), Differentials (WCS/Maya), & WACC    │
│   • Select Regional Viewports & Hurricane Outage Stress Scenarios      │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                      REAL-TIME ANALYTICAL OUTPUT                       │
│   • PyDeck Geospatial Supply Arcs & 3D Refinery Node Heights           │
│   • Node-by-Node Margin Waterfall Table & Net Realizations             │
│   • Interactive Plotly Volumetric Sankey Conversion Matrix             │
│   • LIFO Liquidation Deficit & Tax Liability Alert Banners             │
└────────────────────────────────────────────────────────────────────────┘
23. Installation InstructionsPrerequisitesPython 3.10 or highergit CLI toolSetup Steps# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/VOLT-Terminal.git
cd VOLT-Terminal

# 2. Create a virtual environment
python -m venv venv

# 3. Activate the virtual environment
# On macOS / Linux:
source venv/bin/activate
# On Windows PowerShell:
.\venv\Scripts\Activate.ps1

# 4. Upgrade pip and install required dependencies
pip install --upgrade pip
pip install -r requirements.txt
13. Instructions for Running LocallyExecute the following command from the root directory of the repository:streamlit run app.py
Upon execution, Streamlit will launch the web application local server (typically accessible at http://localhost:8501 in your browser).14. Screenshots & Visual PlaceholdersDashboard Overview & SEC Audit Verification Bar![Dashboard Overview](https://via.placeholder.com/800x400.png?text=VOLT+Dashboard+Overview+%26+SEC+Audit+Bar)Geospatial 3D Supply Chain Map (Phase 5 Global Command Center)![3D Supply Chain Map](https://via.placeholder.com/800x400.png?text=PyDeck+3D+Supply+Chain+Map)Node-by-Node Margin Spread Calculator & Waterfall![Margin Waterfall](https://via.placeholder.com/800x400.png?text=Margin+Spread+Calculator+%26+Waterfall)Automated LIFO Liquidation Event Warning![LIFO Alert Banner](https://via.placeholder.com/800x400.png?text=LIFO+Liquidation+Warning+Banner)15. Testing & Validation StatusSyntax & Execution Validation: Tested locally using Python 3.10 and Streamlit 1.32 across standard web viewports.Math & Formula Verification: Node-by-node margin waterfalls, capital carrying cost equations, and LIFO liquidation trigger logic verified using manual spreadsheet checks.Dataset Integrity: Verified crude capacities, refinery coordinates, and SEC footnote commitments against Valero's 2025 Form 10-K filing.Automated Unit Testing: Automated pytest suites for real-time SEC API ingestion are not yet implemented.16. Known Limitations & AssumptionsSingle-File Architecture: The application logic currently resides within a single file (app.py) for ease of Streamlit deployment.Simplified Yield Formulas: Refining yield profiles rely on three discrete NCI complexity templates rather than multi-component linear programming models.Macro Benchmark Correlation: Assumes fixed freight tariffs and logistics inputs when performing macro WTI price stress testing.Static Disclosure Snippets: SEC EDGAR audit citations are stored as structured internal dictionaries rather than pulled dynamically via live web-scraping requests.17. Future Development Roadmap[ ] Multi-Company Benchmark Registry: Expand parameter presets to include Marathon Petroleum (MPC), Phillips 66 (PSX), and PBF Energy.[ ] SEC EDGAR Automated Scraper: Build an automated REST API ingestion pipeline to update Note 19 and Note 21 tables upon new 10-K/10-Q filings.[ ] Linear Programming Yield Optimizer: Replace template-based yields with a full LP refinery yield optimization solver.[ ] Modular Package Refactoring: Break down app.py into distinct python package sub-modules (/modules, /components, /services).18. License InformationDistributed under the MIT License. See LICENSE for details.19. Project StatusCurrent Version: v1.2.0-stableStatus: Operational portfolio terminal featuring complete Phased Supply Chain Mapping (Phases 1–5), 4-Stage Lifecycle Costing, Margin & Velocity Engines, and LIFO Liquidation Monitoring.

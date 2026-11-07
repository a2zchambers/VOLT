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

[Status Legend: [IMPLEMENTED] | [PARTIAL / SIMULATED] | [PLANNED]]



--------------------------------------------------------------------------------------------------------

FEATURE / MODULE                  | STATUS               | DESCRIPTION
--------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------

Phase 1: Feedstock Sourcing       | [IMPLEMENTED]        | Regional crude slate registry, landed cost 

                                  |                      | simulator (WCS/Maya discounts), DGD renewable 

                                  |                      | feedstocks, and SEC Note 19 obligations.

--------------------------------------------------------------------------------------------------------

Phase 2: Refining Nodes           | [IMPLEMENTED]        | 14-refinery capacity footprint (3.2M BPCD), 

                                  |                      | regional weighted NCI indexer, product yield 

                                  |                      | transformation, and turnaround schedule engine.

--------------------------------------------------------------------------------------------------------

Phase 3: Logistics & Channels     | [IMPLEMENTED]        | Logistics lease commitments registry, freight 

                                  |                      | rate shock simulator, export destination 

                                  |                      | mapping, and Note 21 segment revenue breakdown.

--------------------------------------------------------------------------------------------------------

Phase 4: Unified Terminal         | [IMPLEMENTED]        | Consolidated PyDeck supply map, throughput vs. 

                                  |                      | crack spread margin capture dashboard, and Plotly 

                                  |                      | Sankey volumetric flow diagram.

--------------------------------------------------------------------------------------------------------

Phase 5: Geospatial Command       | [IMPLEMENTED]        | Global/Regional PyDeck viewports, 3D elevation 

                                  |                      | flows, and hurricane outage stress-testing 

                                  |                      | scenario toggle.

--------------------------------------------------------------------------------------------------------

Cost & Velocity Architecture      | [IMPLEMENTED]        | 4-Stage operational hub featuring Valero audited 

                                  |                      | baseline presets vs. custom company parameter 

                                  |                      | override toggles.

--------------------------------------------------------------------------------------------------------

Margin Spread Engine              | [IMPLEMENTED]        | Interactive Node-by-Node margin waterfall 

                                  |                      | calculator isolating landed cost, NCI uplift, 

                                  |                      | OpEx, and compliance drags.

--------------------------------------------------------------------------------------------------------

Supply Chain Velocity             | [IMPLEMENTED]        | 5-stage cash-to-cash lead time calculator 

                                  |                      | (Inbound Transit, Buffer, Processing, DSI, DSO) 

                                  |                      | with capital drag calculations.

--------------------------------------------------------------------------------------------------------

LIFO Staging Matrix               | [IMPLEMENTED]        | Matrix detailing cost drivers, velocity bounds, 

                                  |                      | and LIFO accounting impacts across 4 lifecycle 

                                  |                      | stages with holding time controls.

--------------------------------------------------------------------------------------------------------

LIFO Liquidation Monitor          | [IMPLEMENTED]        | Automated risk engine detecting inventory volume 

                                  |                      | drawdowns below historical base pools and 

                                  |                      | calculating artificial tax/margin spikes.

--------------------------------------------------------------------------------------------------------

Live SEC EDGAR API Scraping       | [PARTIAL / SIMULATED]| SEC citations and verbatim snippets are 

                                  |                      | hardcoded from verified 2025 10-K filings; 

                                  |                      | live automated scraper pipeline staged.

--------------------------------------------------------------------------------------------------------

Multi-Company Benchmark Engine    | [PLANNED]            | Automated side-by-side benchmarking database 

                                  |                      | for Marathon Petroleum (MPC), Phillips 66 (PSX), 

                                  |                      | and PBF Energy.

--------------------------------------------------------------------------------------------------------


# 8. Financial & Operational Calculations

--------------------------------------------------------------------------------------------------------

A. LANDED FEEDSTOCK COST (C_landed)

--------------------------------------------------------------------------------------------------------

Formulas:

  • C_landed,WCS  = (P_WTI - Delta_WCS) + T_Enbridge/TMX

  • C_landed,Maya = (P_WTI - Delta_Maya) + T_Waterborne + F_demurrage

  • C_bar_landed  = Sum_i (C_landed,i * w_i)



Parameters & Specifications:

  • Units     : USD per barrel ($/bbl)

  • Assumptions: Default baseline weights (w_i): Permian WTI (40%), WCS (35%), Maya (25%).

  • Limitations: Assumes pipeline tariffs remain linear regardless of batch volumes.


--------------------------------------------------------------------------------------------------------

B. NCI COMPLEXITY UPLIFT & GROSS REFINING MARGIN (GRM)

--------------------------------------------------------------------------------------------------------

Formulas:

  • U_NCI              = (NCI - 8.0) * 0.35

  • V_adjusted_product = V_basket + U_NCI

  • GRM                = V_adjusted_product - C_bar_landed



Parameters & Specifications:

  • Units     : USD per barrel ($/bbl)

  • Assumptions: Baseline Nelson Complexity Index benchmarked to Valero fleet average (12.7). 

                 Bonus coefficient fixed at $0.35/bbl per NCI point above 8.0.

--------------------------------------------------------------------------------------------------------

C. DAILY CAPITAL CARRYING DRAG (C_carry)

--------------------------------------------------------------------------------------------------------

Formula:

  • C_carry = (C_bar_landed * (WACC / 365)) + F_storage



Parameters & Specifications:

  • Units     : USD per barrel per day ($/bbl/day)

  • Assumptions: Valero baseline WACC set to 8.5%; default daily storage fee set to $0.08/bbl/day.

--------------------------------------------------------------------------------------------------------

D. LIFO LAYER LIQUIDATION MARGIN EXPANSION (Delta M_LIFO)

--------------------------------------------------------------------------------------------------------

Formula:

  • If V_current < V_base_pool:

    Delta M_LIFO = (P_replacement - P_historical_base) * (V_base_pool - V_current)



Parameters & Specifications:

  • Units     : Millions of USD ($M)

  • Assumptions: Base pool baseline anchored to audited historical layer volume (48.0M bbls) 

                 and cost ($42.00/bbl).

  • Limitations: Does not incorporate federal/state income tax rate brackets in calculating 

                 post-tax net income drag.

========================================================================================================

# 9. Data Sourcing & Verification Methodology

====================================================================================================
PUBLIC SEC EDGAR DISCLOSURES & BASELINE ASSUMPTIONS (VALERO ENERGY CORP - CIK: 0001035002)
====================================================================================================

All baseline parameters, asset capacities, contract obligations, and financial segment data integrated within 
the VOLT terminal are sourced directly from Valero Energy Corporation's 2025 Form 10-K SEC filings:

----------------------------------------------------------------------------------------------------
DISCLOSURE SECTION                            METRIC & OPERATIONAL PARAMETER
----------------------------------------------------------------------------------------------------
Item 1: Business - Refining Operations       • 14 Petroleum Refineries globally operated
                                              • Total Throughput Nameplate Capacity: 3.2M BPCD
                                              • Heavy sour and light sweet crude slate slates

Item 8, Note 1: Accounting Policies           • Deferred turnaround maintenance & inspection policy
                                              • Multi-year amortization methodology

Item 8, Note 4: Joint Ventures                • Equity-method investment in Diamond Green Diesel (DGD)
                                              • Renewable diesel nameplate capacity: 1.2 Billion gal/yr

Item 8, Note 19: Commitments & Contingencies   • Take-or-pay pipeline transportation contracts
                                              • Marine throughput commitments: $890 Million (2026)

Item 8, Note 21: Segment Disaggregation       • External product-line revenue breakdown:
                                                - Refined Products: $132.4 Billion
                                                - Renewable Diesel: $5.2 Billion
                                                - Ethanol: $4.8 Billion
----------------------------------------------------------------------------------------------------


# 10. Key Financial & Operational Metrics
Nelson Complexity Index (NCI): A metric quantifying the secondary conversion capacity of a petroleum refinery relative to primary crude distillation. Higher NCI enables heavy, high-sulfur crude processing into high-value light products.3-2-1 Crack Spread: A gross margin benchmark representing the yield from three barrels of crude oil into two barrels of gasoline and one barrel of distillate (diesel/jet fuel).
Days Sales of Inventory (DSI): The average temporal duration raw feedstock and finished products are held in network tankage before final sale.
Take-or-Pay Minimum Volume Obligation (MVO): Unconditional contractual commitments requiring minimum payments to pipeline and terminal operators regardless of actual throughput volume utilized.
Renewable Identification Numbers (RINs): Tradable regulatory credits generated under the EPA Renewable Fuel Standard (RFS) used to quantify refiners' blending compliance obligations.

# 11. Application Workflow
┌────────────────────────────────────────────────────────────────────────┐
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

# 12. Installation Instructions
  Prerequisites
    Python 3.10 or highergit CLI toolSetup Steps

1. Clone the repository
git clone https://github.com/YOUR_USERNAME/VOLT-Terminal.git
cd VOLT-Terminal

2. Create a virtual environment
python -m venv venv

3. Activate the virtual environment
  On macOS / Linux:
    source venv/bin/activate
  On Windows PowerShell:
    .\venv\Scripts\Activate.ps1

4. Upgrade pip and install required dependencies
pip install --upgrade pip
pip install -r requirements.txt

# 13. Instructions for Running Locally
Execute the following command from the root directory of the repository:streamlit run app.py
Upon execution, Streamlit will launch the web application local server (typically accessible at http://localhost:8501 in your browser).

# 14. Screenshots & Visual Placeholders
Dashboard Overview & SEC Audit Verification Bar![Dashboard Overview](https://via.placeholder.com/800x400.png?text=VOLT+Dashboard+Overview+%26+SEC+Audit+Bar)
Geospatial 3D Supply Chain Map (Phase 5 Global Command Center)![3D Supply Chain Map](https://via.placeholder.com/800x400.png?text=PyDeck+3D+Supply+Chain+Map)
Node-by-Node Margin Spread Calculator & Waterfall![Margin Waterfall](https://via.placeholder.com/800x400.png?text=Margin+Spread+Calculator+%26+Waterfall)
Automated LIFO Liquidation Event Warning![LIFO Alert Banner](https://via.placeholder.com/800x400.png?text=LIFO+Liquidation+Warning+Banner)

# 15. Testing & Validation Status
Syntax & Execution Validation: Tested locally using Python 3.10 and Streamlit 1.32 across standard web viewports.
Math & Formula Verification: Node-by-node margin waterfalls, capital carrying cost equations, and LIFO liquidation trigger logic verified using manual spreadsheet checks.
Dataset Integrity: Verified crude capacities, refinery coordinates, and SEC footnote commitments against Valero's 2025 Form 10-K filing.
Automated Unit Testing: Automated pytest suites for real-time SEC API ingestion are not yet implemented.

# 16. Known Limitations & Assumptions
Single-File Architecture: The application logic currently resides within a single file (app.py) for ease of Streamlit deployment.
Simplified Yield Formulas: Refining yield profiles rely on three discrete NCI complexity templates rather than multi-component linear programming models.
Macro Benchmark Correlation: Assumes fixed freight tariffs and logistics inputs when performing macro WTI price stress testing.
Static Disclosure Snippets: SEC EDGAR audit citations are stored as structured internal dictionaries rather than pulled dynamically via live web-scraping requests.

# 17. Future Development Roadmap
[ ] Multi-Company Benchmark Registry: Expand parameter presets to include Marathon Petroleum (MPC), Phillips 66 (PSX), and PBF Energy.
[ ] SEC EDGAR Automated Scraper: Build an automated REST API ingestion pipeline to update Note 19 and Note 21 tables upon new 10-K/10-Q filings.
[ ] Linear Programming Yield Optimizer: Replace template-based yields with a full LP refinery yield optimization solver.
[ ] Modular Package Refactoring: Break down app.py into distinct python package sub-modules (/modules, /components, /services).

# 18. License Information
Distributed under the MIT License. See LICENSE for details.

# 19. Project Status
Current Version: v1.2.0-stableStatus: Operational portfolio terminal featuring complete Phased Supply Chain Mapping (Phases 1–5), 4-Stage Lifecycle Costing, Margin & Velocity Engines, and LIFO Liquidation Monitoring.

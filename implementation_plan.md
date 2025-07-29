# Implementation Plan

Project Goal: Develop an AI-assisted system to scan for emerging issues related to societal 'collapse' and 'renewal', and use them to generate 'futures provocations' for the sustainability community.

---
### General Project Notes

**Memory Bank System:**
This project will use a Multi-File Directory System for logging, as agreed upon on 2025-07-29. All logs will be stored in the `/Memory` directory, with subdirectories created for each project phase. Individual task logs will be stored as separate `.md` files within the relevant phase directory. This structure is defined in `Memory/README.md`.

---
## Phase 1: Feasibility Study - Module 1 (Scanning) - Agent Group Beta (Agent_Scanner)

### Task 1.1 - Agent_Scanner: Research and Propose Aggregator/Source Strategy
Objective: To define a clear, feasible method for creating a unified feed of articles for analysis from across the internet.
1.  Review Initial Sources.
    - The User will provide a list of initial sources to mirror Ian Christie's work (e.g., resilience.org, earthbound.report, Hard Art, etc.). Compile this list.
2.  Evaluate Aggregation Tools.
    - Research and identify suitable RSS aggregator services or libraries to collect content from the defined sources.
    - Guidance: Consider factors like ease of use, cost, and API availability.
3.  Propose a Unified Feed Solution.
    - Document a recommended approach to consolidate the sources into a single, machine-readable feed for the next steps.

### Task 1.2 - Agent_Scanner: Develop "Collapse" vs. "Renewal" Filtering Logic
Objective: To create and test a method for classifying incoming articles as related to 'collapse', 'renewal', or neither.
1.  Implement 'Collapse' Filter.
    - Develop an initial filter based on a simple text search for relevant keywords (e.g., 'collapse').
2.  Design 'Renewal' Filter.
    - Research and propose a more nuanced, LLM-based approach for identifying 'renewal', which is semantically more complex.
    - Guidance: The goal is feasibility testing, not a production-grade model.
3.  Define and Log Filter Output.
    - For any given article, the process should output the original URL/text along with its classification ('collapse', 'renewal', 'other').

### Task 1.3 - Agent_Scanner: Develop Hit Classification and Tagging Logic
Objective: To tag relevant articles using standard futures/foresight classification systems.
1.  Implement STEEPLE Tagging.
    - Develop a process (e.g., using LLM prompting with clear definitions) to assign one or more STEEPLE tags (Social, Technological, Economic, Environmental, Political, Legal, Ethical) to an article.
2.  Implement Molitor S-Curve Tagging.
    - The User will provide a training deck on Graham Molitor's framing model.
    - Develop a process to classify an article based on the S-curve stages (e.g., Framing, Advancing, Resolving).
3.  Standardize Tag Output.
    - Ensure the output for a tagged article is a structured format (e.g., JSON) containing the article and a list of its assigned tags.

---
## Phase 2: Feasibility Study - Module 2 (Sense-Making) - Agent Group Alpha (Agent_Sense_Maker)

### Task 2.1 - Agent_Sense_Maker: Develop Thematic Analysis Logic
Objective: To create a process for identifying and synthesizing common themes from the collection of classified articles generated in Phase 1.
1.  Design Theme Identification Method.
    - Develop a methodology for processing a batch of articles from the Scanning module.
    - Guidance: This will involve using an LLM API for semantic analysis. The method should focus on techniques like generating embeddings for articles, performing semantic clustering, and using summarization prompts to articulate the resulting themes.
2.  Define "Theme" Output Structure.
    - Determine a structured format for a "theme."
    - Guidance: The output should likely include a concise theme title, a short descriptive paragraph, and references to the source articles that support it.

### Task 2.2 - Agent_Sense_Maker: Develop "Seed of Change" Generation from Themes
Objective: To create a reliable process for transforming a synthesized theme into a "Seed of Change" narrative.
1.  Adapt Transformation Logic.
    - Develop a prompt or function that takes a "theme" (as defined in Task 2.1) as input.
    - The logic must extrapolate this theme into a short narrative describing what the world would be like if this theme became a mainstream way the world was organized.
2.  Test and Refine Logic.
    - Create example themes (or use outputs from Task 2.1 tests) to test the generation process.

### Task 2.3 - Agent_Sense_Maker: Develop Mini-Scenario Combination Logic
Objective: To create a process for combining multiple "Seeds of Change" (generated from themes) into a coherent "what if" mini-scenario.
1.  Design Combination Strategy.
    - Develop logic to select either a pair or a trio of "Seeds of Change" for combination.
    - Guidance: Selections must be from different domains (e.g., Social x Economic). The STEEPLE classification from Phase 1 will be relevant here.
2.  Implement Narrative Generation.
    - Create a prompt or function that takes the selected Seeds as input and generates a short narrative (250-300 words).
3.  Define Associated Media Prompts.
    - As part of the output, generate a concise text prompt suitable for an image generation model that captures the essence of the mini-scenario.

---
## Phase 3: Feasibility Study Review & PoC Planning - Agent Group Gamma (Manager_Agent)

### Task 3.1 - Manager_Agent: Synthesize Feasibility Findings
Objective: To consolidate all findings from Phases 1 and 2 into a comprehensive Feasibility Study report.
1.  Review All Memory Bank Logs.
    - Analyze the outputs, challenges, and successes documented by Agent_Scanner and Agent_Sense_Maker.
2.  Draft Feasibility Report.
    - Summarize the recommended and tested processes for both the Scanning and Sense-Making modules.
    - Identify key dependencies and remaining open questions.

### Task 3.2 - Manager_Agent: Develop Proof of Concept (PoC) Implementation Plan
Objective: To create a detailed, actionable plan for the PoC stage based on the feasibility results.
1.  Define PoC Scope.
    - In collaboration with the User, determine the exact features and workflows to be built for the PoC.
2.  Create New Implementation Plan.
    - Draft a new `Implementation_Plan_PoC.md` with detailed phases and tasks for the development of the Proof of Concept.

---
## Note on Handover Protocol
For long-running projects or situations requiring context transfer (e.g., exceeding LLM context limits, changing specialized agents), the APM Handover Protocol should be initiated. This ensures smooth transitions and preserves project knowledge. Detailed procedures are outlined in the framework guide:
`prompts/01_Manager_Agent_Core_Guides/05_Handover_Protocol_Guide.md`

The current Manager Agent or the User should initiate this protocol as needed.
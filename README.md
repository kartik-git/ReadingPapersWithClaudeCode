# Research Paper → Toy Implementation (Claude Project)

This repository configures Claude to transform **research papers into runnable, pedagogical Jupyter notebooks**.

The goal is **understanding through building**, not reproduction or benchmarking.

When correctly set up, you can:
- Upload a research paper PDF
- Ask Claude to “implement this paper”
- Receive a CPU-only, step-by-step notebook that explains the algorithm by running it

---

## Repository Structure

.
├── CLAUDE.md
├── README.md
└── context/
├── skill.md
├── runtime.md
├── output_contract.md
├── notebook_template.md
└── checklists.md

### What each file does

- **`CLAUDE.md`**  
  The *primary system instruction*. Claude reads this first and treats it as the project’s operating contract.

- **`context/skill.md`**  
  Frozen definition of the “Research Paper → Toy Implementation” skill.

- **`context/runtime.md`**  
  Execution guarantees (Colab CPU, Python version, dependency rules).

- **`context/output_contract.md`**  
  Defines what “done” means. Prevents partial or low-quality outputs.

- **`context/notebook_template.md`**  
  Canonical structure for pedagogical notebooks.

- **`context/checklists.md`**  
  Guardrails to maintain quality and avoid common failure modes.

---

## How to Use (Claude Web – Projects UI)

This is the **recommended setup for most users**.

### Step 1: Create a Claude Project
1. Open Claude (web)
2. Go to **Projects**
3. Click **New Project**
4. Name it something like:  
   **“Research Paper → Toy Implementation”**

### Step 2: Add Files to the Project
Upload the following files into the project:
- `CLAUDE.md`
- Entire `context/` folder (all files inside it)

Claude automatically treats these as **persistent system context** for the project.

### Step 3: Upload a Paper
Inside the project:
- Upload a research paper PDF (or multiple PDFs)

### Step 4: Trigger the Skill
Use prompts like:
- “Implement this paper as a toy notebook”
- “Turn this paper into a Colab-friendly implementation”
- “Help me understand this paper by building it”

Claude will:
- Read the paper
- Extract the core algorithm
- Build a runnable Jupyter notebook
- Explain the algorithm through execution, prints, and plots

No additional configuration is required.

## How to Use (Claude Code)

If you are using **Claude Code**, this repository is designed to work as a **drop-in project configuration**.

### Option A: Project Root (Recommended)

Place these files directly at the root of your Claude Code project:

your-project/
├── CLAUDE.md
└── context/


Claude Code will automatically:
- Load `CLAUDE.md` as the system instruction
- Make all files under `context/` available as long-lived guidance

### Option B: Explicit Config Reference

If your setup requires explicit configuration (e.g., `.claude/config`):

1. Ensure `CLAUDE.md` is referenced as the system prompt
2. Ensure the `context/` directory is included in the project context
3. Do **not** inline or merge these files — Claude relies on file boundaries
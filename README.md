# AI Writing Skills

A collection of prompts and guidelines for AI-assisted academic and research writing in medical AI.

## Skills

### 1. Protocol Writing (`protocol-writing.md`)
Comprehensive guide for writing clinical research protocols for AI-based diagnostic studies, validation trials, and retrospective analyses.

**Includes:**
- 16-section protocol structure
- Style guidelines
- Section length reference
- Submission checklist

### 2. Manuscript Writing - TRIPOD-AI (`manuscript-writing-tripod.md`)
Guidelines for writing AI papers following TRIPOD+AI reporting standards.

**Includes:**
- Results section structure
- Table templates
- Visual presentation best practices
- Transparency requirements

### 3. Manuscript Review (`manuscript-review.md`)
Section-by-section checklist for reviewing medical AI manuscripts.

**Includes:**
- Background, Methods, Results, Tables, Discussion, and Abstract checklists
- Success criteria for each section
- Numerical formatting rules
- Forbidden patterns reference

### 4. CIHR Grant Writing (`CIHR_RCT_WRITING.md`)
Section-by-section guide for writing CIHR Project Grant applications.

**Includes:**
- Full section-by-section structure (Need, Design, Management, General Considerations)
- Weighted scoring rubrics for each subsection
- Fill-in-the-blank templates
- Appendices for CIHR-specific language, study type adaptation, and common reviewer critiques

---

## Installation

### Claude Code (Global Slash Commands)

Install these as global slash commands available in every project on your machine.

**1. Create the commands directory:**

```bash
mkdir -p ~/.claude/commands
```

**2. Copy each skill file:**

```bash
cp protocol-writing.md ~/.claude/commands/protocol-writing.md
cp manuscript-writing-tripod.md ~/.claude/commands/manuscript-writing-tripod.md
cp manuscript-review.md ~/.claude/commands/manuscript-review.md
cp CIHR_RCT_WRITING.md ~/.claude/commands/cihr-grant-writing.md
```

**3. Add frontmatter to each file** (gives Claude Code the description for slash command discovery):

```bash
sed -i '' '1i\
---\
description: Guide for writing high-quality clinical research protocols for AI-based diagnostic studies, validation trials, and retrospective analyses\
---\
' ~/.claude/commands/protocol-writing.md

sed -i '' '1i\
---\
description: Guide for writing AI paper results following TRIPOD+AI guidelines, covering participants, model development, performance metrics, and presentation best practices\
---\
' ~/.claude/commands/manuscript-writing-tripod.md

sed -i '' '1i\
---\
description: Section-by-section checklist for reviewing medical AI manuscripts with success criteria for Background, Methods, Results, Tables, Discussion, and Abstract\
---\
' ~/.claude/commands/manuscript-review.md

sed -i '' '1i\
---\
description: Section-by-section guide for writing CIHR Project Grant applications, covering RCTs, AI/technology, observational studies, with scoring rubrics and templates\
---\
' ~/.claude/commands/cihr-grant-writing.md
```

**4. Use them anywhere in Claude Code:**

```
/protocol-writing
/manuscript-writing-tripod
/manuscript-review
/cihr-grant-writing
```

> **Note:** For project-specific commands (instead of global), place the files in `.claude/commands/` inside your project directory instead.

---

### Claude Desktop (Projects)

Claude Desktop uses **Projects** to store reusable instructions and knowledge.

**1.** Open Claude Desktop and go to **Projects** (left sidebar).

**2.** Create a new project (e.g., "Academic Writing Skills").

**3.** Add each skill as project knowledge:
- Click **"Add content"** in the project knowledge section
- Select **"Add text content"** (or drag and drop the `.md` file)
- Paste the full contents of each `.md` file as a separate knowledge entry:
  - `protocol-writing.md`
  - `manuscript-writing-tripod.md`
  - `manuscript-review.md`
  - `CIHR_RCT_WRITING.md`

**4.** (Optional) Add project instructions:

In the project's **"Instructions"** field, add:

```
You are an academic writing assistant specializing in medical AI research.
When the user asks you to write or review a protocol, manuscript, or grant,
use the relevant skill from the project knowledge to guide your output.
Always follow the structure, style guidelines, and checklists provided.
For manuscript reviews, use the section-by-section checklist approach.
```

**5.** Start a new conversation within that project to use the skills.

---

### ChatGPT / Codex (Custom GPTs or System Prompts)

#### Option A: Custom GPT (Persistent)

**1.** Go to [https://chat.openai.com/gpts/editor](https://chat.openai.com/gpts/editor)

**2.** Create a new GPT with the following settings:

- **Name:** Academic Writing Assistant
- **Description:** Helps write research protocols, TRIPOD-AI manuscripts, and CIHR grant applications
- **Instructions:** Paste the following system prompt:

```
You are an academic writing assistant specializing in medical AI research.
You have access to four writing skills as knowledge files.
When the user asks you to write or review a protocol, use "protocol-writing.md".
When the user asks you to write a manuscript, use "manuscript-writing-tripod.md".
When the user asks you to review a manuscript, use "manuscript-review.md".
When the user asks you to write or review a CIHR grant, use "cihr-grant-writing.md".
Always follow the structure, style guidelines, scoring rubrics, and checklists provided in each skill.
```

**3.** Upload the 4 `.md` files under the **"Knowledge"** section.

**4.** Save and use the GPT.

#### Option B: ChatGPT Projects (Simpler)

**1.** In ChatGPT, create a new **Project** (left sidebar).

**2.** Add each `.md` file to the project's **Files** section.

**3.** Add project instructions (same as the system prompt above).

**4.** Start a conversation within the project.

#### Option C: Paste into a Single Conversation

If you don't need persistence, simply paste the contents of the relevant `.md` file at the start of any ChatGPT conversation.

---

### Notion

#### Option A: Dedicated Database

**1.** Create a new Notion database called "AI Writing Skills".

**2.** Add the following properties:
- **Name** (Title) -- the skill name
- **Category** (Select) -- Protocol / Manuscript / Grant
- **Tags** (Multi-select) -- e.g., TRIPOD-AI, CIHR, Diagnostic AI

**3.** Create one page per skill:

|| Name | Category | Tags |
||------|----------|------|
|| Protocol Writing | Protocol | Diagnostic AI, Validation |
|| TRIPOD-AI Manuscript Writing | Manuscript | TRIPOD-AI, Reporting |
|| Manuscript Review | Review | Checklist, Quality Control |
|| CIHR Grant Writing | Grant | CIHR, RCT, AI/Technology |

**4.** In each page, paste the full contents of the corresponding `.md` file. Notion will automatically render the markdown headings, tables, checklists, and code blocks.

#### Option B: Single Page with Toggles

**1.** Create a new Notion page called "AI Writing Skills".

**2.** Add 4 toggle headings (type `/toggle heading` or `/toggle`):

- **Protocol Writing** -- paste contents of `protocol-writing.md`
- **TRIPOD-AI Manuscript Writing** -- paste contents of `manuscript-writing-tripod.md`
- **Manuscript Review** -- paste contents of `manuscript-review.md`
- **CIHR Grant Writing** -- paste contents of `CIHR_RCT_WRITING.md`

Each toggle collapses the full skill so you can expand only what you need.

#### Option C: Notion AI Integration

If you have **Notion AI** enabled:

**1.** Add the skills as pages (Option A or B above).

**2.** When using Notion AI, reference the skill page:
- Type `@Protocol Writing` to link the page
- Then ask Notion AI to "write a protocol following the structure in @Protocol Writing"

Notion AI will use the linked page as context.

---

## Quick Reference

|| Skill | File | Claude Code | Claude Desktop | ChatGPT | Notion |
||-------|------|-------------|----------------|---------|--------|
|| Protocol Writing | `protocol-writing.md` | `/protocol-writing` | Project knowledge | GPT knowledge file | Database page or toggle |
|| TRIPOD-AI Manuscript | `manuscript-writing-tripod.md` | `/manuscript-writing-tripod` | Project knowledge | GPT knowledge file | Database page or toggle |
|| Manuscript Review | `manuscript-review.md` | `/manuscript-review` | Project knowledge | GPT knowledge file | Database page or toggle |
|| CIHR Grant Writing | `CIHR_RCT_WRITING.md` | `/cihr-grant-writing` | Project knowledge | GPT knowledge file | Database page or toggle |

---

## License

MIT License - HeartWise.AI

## Version

v1.2.0 - Added Manuscript Review skill with section-by-section checklists

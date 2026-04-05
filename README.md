# Claude Code Workshop

> Build your own AI agent in 2 hours — no coding required.

---

## Before the Workshop (~10 min setup)

### 1. Sign up for Claude (free for 1 week)

**https://claude.ai/referral/I6jwoLOL1A**

Create your account and log in.

### 2. Install these things

**Mac users — run this first (takes a few minutes):**
```
xcode-select --install
```
Open Terminal (`Cmd + Space` → type "Terminal" → Enter), paste the above, click "Install" on the popup.

**Everyone — install Node.js:**
Go to **https://nodejs.org** → click the green **LTS** button → run the installer.

**Everyone — install Claude Code:**
Open Terminal (Mac) or PowerShell (Windows) and paste:
```
npm install -g @anthropic-ai/claude-code
```

### 3. Think about your workflows

Think of **2-3 repetitive tasks** from your job. We'll turn these into AI skills.

| Role | Examples |
|------|----------|
| Product | Analyzing call transcripts, summarizing feature requests |
| Sales | Validating leads against ICP, writing outreach emails |
| Marketing | Creating ad copy, writing blog drafts |
| Ops / PM | Status updates, meeting summaries |

### 4. Arrive 15 minutes early

We'll help troubleshoot any setup issues before we start.

---

## During the Workshop

### Terminal Basics (4 commands — that's it)

Open your terminal:
- **Mac**: `Cmd + Space` → type **Terminal** → Enter
- **Windows**: Start → type **PowerShell** → Enter

Think of the terminal as **texting your computer**.

```
echo hello
```
> Repeats what you said. The terminal is listening!

```
ls
```
> Shows what's in your current folder. Like opening Finder.

```
mkdir my-agent
```
> Creates a new folder called "my-agent".

```
cd my-agent
```
> Goes inside that folder. Everything we do today lives here.

---

### Launch Claude Code

```
claude
```

It will ask you to log in — **use the account you created with the referral link.** Follow the browser prompt.

Once you're in, try:
```
Hi! What can you do?
```

---

### Create Your CLAUDE.md

A **CLAUDE.md** is a job description for Claude. It reads this file every time it starts working in your folder.

Paste this into Claude Code (fill in your details):

```
Help me create a CLAUDE.md file. Here's my info:

- I am a [YOUR ROLE] at [YOUR COMPANY]
- I work on [brief description of what you do]
- Tools I use daily: [e.g., Notion, Google Sheets, Slack, Salesforce, Excel, Figma]
- I prefer a [formal / casual / professional] tone in my work
- My common tasks include: [list 3-5 things you do regularly]

Create a CLAUDE.md that gives you context about me so you can assist me better in future conversations.
```

After Claude creates the file, read through it. If something's missing:
*"Update the CLAUDE.md to also mention that I [whatever was missing]"*

---

### Discover and Build Your Skills

A **skill** is a saved playbook. Instead of typing a long prompt every time, you save it as `/skill-name` and Claude knows what to do.

Paste this prompt:

```
I want you to help me set up Claude Code skills for my daily work. First, ask me these questions one by one:

1. What domain am I in? (product, sales, marketing, ops, HR, finance, design, etc.)
2. What are 3-5 things I do regularly that are repetitive or follow a pattern?
3. What tools do I use for these tasks?
4. What does a good output look like for each task?

Based on my answers, suggest 3-5 skills that would save me the most time. For each skill:
- Explain what it does in one sentence
- Show me a sample input → output

Then ask me which skills I want to build. For each one I pick, create the skill file with:
- Clear instructions for the task
- The right output format
- An --improve flag so I can give feedback and make it better over time

Create each skill so I can invoke it with /skill-name.
```

**Example skills by role:**

| Role | Skill | What it does |
|------|-------|-------------|
| Product | `/analyze-call` | Paste a call transcript → pain points, feature requests, next steps |
| Product | `/prioritize-features` | Paste feature requests → prioritized list with impact/effort |
| Sales | `/validate-lead` | Paste company details → ICP fit score with reasons |
| Sales | `/cold-email` | Paste company info → personalized outreach under 150 words |
| Marketing | `/ad-copy` | Describe angle + audience → 3-4 ad copy variations |
| Marketing | `/blog-draft` | Paste outline → full blog draft with SEO structure |
| Ops / PM | `/status-update` | Paste rough notes → professional stakeholder email |
| Ops / PM | `/summarize-notes` | Paste meeting notes → summary + action items + decisions |

---

### Test with Sample Files

Sample files are in the `samples/` folder of this repo:

| File | What it is |
|------|-----------|
| `samples/product/call_transcript.md` | Product discovery call transcript |
| `samples/product/feature_requests.md` | 10 feature requests with raw notes |
| `samples/sales/icp_definition.md` | Ideal Customer Profile document |
| `samples/sales/company_list.csv` | 20 companies to validate against ICP |
| `samples/marketing/ad_brief.md` | Ad campaign brain dump |
| `samples/marketing/blog_outline.md` | Blog content outline |

Copy files into your folder and tell Claude:
```
Read the file call_transcript.md and analyze it
```

---

## Power Features

**Paste images** — Paste screenshots directly into Claude Code. "Extract data from this", "Write variations inspired by this".

**Plan mode** — Type `/plan` for bigger tasks. Claude outlines steps before executing.

**Skip permissions** — Press **Shift + Tab** to toggle. Choose "Allow all" for trusted workflows.

**Browse skills** — Type `/` to see all your saved skills.

**Read any file** — Drop CSV, PDF, text, images into your folder and ask Claude about them.

---

## Making Your Agent Smarter

### Feedback Loop

Give feedback after running any skill:
```
/cold-email --improve "keep it under 100 words and always end with a question"
```
The skill updates permanently. Every future run uses your feedback.

### Memory

Ask Claude to remember things across all conversations:
```
Remember that I prefer bullet points over paragraphs
Remember that when I say "client" I mean enterprise customers
```

### Update CLAUDE.md

If Claude consistently gets something wrong:
```
Update the CLAUDE.md to mention that I always want outputs in table format
```

**The cycle:** Run skill → notice what's off → `--improve` → repeat until perfect → stays perfect forever.

---

## Git Setup (end of workshop)

Save your work with version control. Git = "save points" for your project.

**Mac** (skip if Xcode tools already installed): `xcode-select --install`
**Windows**: Download from https://git-scm.com/download/win

```
git init
git add .
git commit -m "Initial setup: CLAUDE.md and skills"
```

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `command not found: npm` | Install Node.js from https://nodejs.org |
| `command not found: claude` | Run `npm install -g @anthropic-ai/claude-code` |
| Login not working | Log in at https://claude.ai first, then retry in terminal |
| Permission denied (Mac) | Use `sudo npm install -g @anthropic-ai/claude-code` |
| Skills not showing | `cd my-agent` then type `/` |

---

## What's Next?

1. **Use it daily** — the more you use it, the better it gets
2. **Build more skills** — any repetitive task = a `/skill-name`
3. **Keep improving** — `--improve` whenever output isn't perfect
4. **Share with teammates** — skill files can be copied to anyone's setup
5. **Docs** — https://docs.anthropic.com/en/docs/claude-code

---

**Workshop by [Himanshu Saleria](https://www.linkedin.com/in/himanshu-saleria/)**

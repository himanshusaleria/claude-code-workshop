# Workshop Guide — Step by Step

> Follow along during the workshop. Every command you need is here — just copy and paste.

---

## 1. Terminal Basics (the only 4 commands you need)

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
> Shows what's in your current folder. Like opening Finder or File Explorer.

```
mkdir my-agent
```
> Creates a new folder called "my-agent".

```
cd my-agent
```
> Goes inside that folder. Everything we do today lives here.

---

## 2. Launch Claude Code

```
claude
```

It will ask you to log in. **Use the account you created with the referral link.** Choose "Log in with your Claude account" and follow the browser prompt.

Once you're in, try:

```
Hi! What can you do?
```

If Claude responds, you're ready.

---

## 3. Create Your CLAUDE.md

A **CLAUDE.md** is a job description for Claude. Every time Claude starts working in your folder, it reads this file first.

Paste this into Claude Code (fill in your details first):

```
Help me create a CLAUDE.md file. Here's my info:

- I am a [YOUR ROLE] at [YOUR COMPANY]
- I work on [brief description of what you do]
- Tools I use daily: [e.g., Notion, Google Sheets, Slack, Salesforce, Excel, Figma]
- I prefer a [formal / casual / professional] tone in my work
- My common tasks include: [list 3-5 things you do regularly]

Create a CLAUDE.md that gives you context about me so you can assist me better in future conversations.
```

After Claude creates the file:
- Read through it — does it capture your role well?
- If something's missing: *"Update the CLAUDE.md to also mention that I [whatever was missing]"*

---

## 4. Discover and Build Your Skills

A **skill** is a saved playbook. Instead of typing a long prompt every time, you save it with a name like `/weekly-report` and Claude knows exactly what to do.

Paste this prompt into Claude Code:

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

Claude will walk you through it. Just answer honestly about your work.

**Examples of skills by role:**

| Role | Skill | What it does |
|------|-------|-------------|
| Product | `/analyze-call` | Paste a call transcript → key pain points, feature requests, next steps |
| Product | `/prioritize-features` | Paste feature requests → prioritized list with impact/effort scoring |
| Sales | `/validate-lead` | Paste company details → ICP fit score with reasons |
| Sales | `/cold-email` | Paste company info → personalized outreach email under 150 words |
| Marketing | `/ad-copy` | Describe angle + audience → 3-4 ad copy variations |
| Marketing | `/blog-draft` | Paste outline → full blog draft with SEO structure |
| Ops / PM | `/status-update` | Paste rough notes → professional stakeholder email |
| Ops / PM | `/summarize-notes` | Paste meeting notes → summary + action items + decisions |

---

## 5. Test with Sample Files

We've included sample files in `samples/` for you to test with:

| File | What it is | Try with |
|------|-----------|----------|
| `samples/product/call_transcript.md` | Product discovery call | `/analyze-call` |
| `samples/product/feature_requests.md` | 10 feature requests | `/prioritize-features` |
| `samples/sales/icp_definition.md` | Ideal Customer Profile | `/validate-lead` |
| `samples/sales/company_list.csv` | 20 companies to validate | `/validate-lead` |
| `samples/marketing/ad_brief.md` | Ad campaign brain dump | `/ad-copy` |
| `samples/marketing/blog_outline.md` | Blog content outline | `/blog-draft` |

Copy sample files into your folder and tell Claude:
```
Read the file call_transcript.md and analyze it
```

Or paste the contents directly.

---

## 6. Power Features

### Paste Images and Screenshots
Paste images directly into Claude Code:
- Screenshot of a spreadsheet → "Extract this data into a table"
- Competitor's ad → "Write 3 variations inspired by this"
- Whiteboard photo → "Turn these notes into action items"

### Plan Mode
For bigger tasks, ask Claude to plan before acting:
```
/plan
```
Claude outlines steps and asks for approval before executing. Like asking your intern to show their approach before starting.

### Skip Permission Prompts
Claude asks permission before every file read/write. To let it run freely:
- Press **Shift + Tab** to toggle permission modes
- Choose "Allow all for this session" for trusted workflows

### Browse Your Skills
```
/
```
Type `/` to see all your saved skills.

### Read Any File
Drop any file into your folder:
```
Read report.csv and tell me the top 5 trends
```
Works with CSV, PDF, text, markdown, images, and more.

---

## 7. Making Your Agent Smarter Over Time

### The Feedback Loop

Your agent gets better every time you use it.

**Run a skill** → look at the output → **give feedback**:
```
/cold-email --improve "keep it under 100 words and always end with a question"
```

The skill updates permanently. Every future run uses your feedback.

**The cycle:**
1. Run a skill
2. Notice what's not right
3. Use `--improve` to fix it
4. Repeat until perfect
5. It stays perfect forever

### Memory

Ask Claude to remember things across ALL conversations:
```
Remember that I prefer bullet points over paragraphs
Remember that when I say "client" I mean enterprise customers
Remember that all my reports should use INR, not USD
```

### Update CLAUDE.md Over Time

Your CLAUDE.md should evolve. If Claude consistently gets something wrong:
```
Update the CLAUDE.md to mention that I always want outputs in table format
```

---

## 8. Git Setup (Version Control)

Now let's save your work properly. Git is like **"save points"** — you can always go back.

### Install Git (if not already installed)

**Mac** (skip if you installed Xcode tools earlier):
```
xcode-select --install
```

**Windows:**
Go to **https://git-scm.com/download/win** → run the installer (Next through everything).

### Set Up Git in Your Project

```
git init
```
> Turns your folder into a Git project.

```
git add .
```
> Stages all your files.

```
git commit -m "Initial setup: CLAUDE.md and skills"
```
> Saves a snapshot. You can always go back to this point.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `command not found: npm` | Install Node.js from https://nodejs.org |
| `command not found: claude` | Run `npm install -g @anthropic-ai/claude-code` |
| Login not working | Log in at https://claude.ai in browser first, then retry |
| Claude is slow | Check internet, try `/clear`, or restart terminal |
| Permission denied (Mac) | Use `sudo npm install -g @anthropic-ai/claude-code` |
| Skills not showing | Make sure you're in the right folder (`cd my-agent`), type `/` |

---

## What's Next?

1. **Use it daily** — the more you use it, the better it gets
2. **Build more skills** — any repetitive task can become a `/skill-name`
3. **Keep improving** — use `--improve` whenever output isn't perfect
4. **Share with teammates** — skill files can be copied to anyone's setup
5. **Explore the docs** — https://docs.anthropic.com/en/docs/claude-code

---

**Workshop by [Himanshu Saleria](https://www.linkedin.com/in/himanshu-saleria/)**

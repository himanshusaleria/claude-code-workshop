# Claude Code Workshop

> Build your own AI agent in 2 hours — no coding required.

---

## Before the Workshop

### 1. Get Claude Code Free for 1 Week

Click this link to get **1 week of Claude Code free**:

**https://claude.ai/referral/I6jwoLOL1A**

Sign up and log in. You'll use this account during the workshop.

### 2. Install Node.js

Go to **https://nodejs.org** and click the big green **LTS** button.

- **Mac**: Open the downloaded `.pkg` file → click through (Continue → Continue → Install → Close)
- **Windows**: Open the downloaded `.msi` file → click through (Next → Next → Install → Finish)

You won't need to open Node.js directly — it just needs to be installed on your machine.

### 3. Install Claude Code

**On Mac:**
1. Press `Cmd + Space`, type **Terminal**, press Enter
2. Paste this and press Enter:

```
npm install -g @anthropic-ai/claude-code
```

**On Windows:**
1. Click Start, type **PowerShell**, press Enter
2. Paste this and press Enter:

```
npm install -g @anthropic-ai/claude-code
```

Wait about 30 seconds. If you see no red error messages, you're good.

### 4. Please arrive 15 minutes early

We'll have the team ready to help you troubleshoot any setup issues before the workshop starts. If you run into problems with installation, don't worry — just come early and we'll fix it together.

### 5. Think about YOUR workflow

Before you arrive, think about **2-3 repetitive tasks** from your job. These are things you do regularly that follow a pattern. We'll build AI skills around them.

Examples by role:

| Role | Example Workflows |
|------|------------------|
| **Product** | Analyzing call transcripts, summarizing feature requests, writing PRDs |
| **Sales** | Validating leads against ICP, writing cold outreach, prepping for calls |
| **Marketing** | Creating ad copy, writing blog drafts, generating social posts |
| **Ops / PM** | Writing status updates, formatting stakeholder emails, meeting summaries |
| **HR** | Writing JDs, screening questions, onboarding checklists |
| **Finance** | Expense categorization, report summaries, variance analysis |

---

## At the Workshop

### Terminal Basics (the only 4 commands you need)

First, open your terminal:
- **Mac**: `Cmd + Space` → type **Terminal** → Enter
- **Windows**: Start → type **PowerShell** → Enter

Think of the terminal as **texting your computer**. Here are the 4 messages it understands:

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
> Goes inside that folder. Now everything you do happens here.

That's it. Those 4 commands are all the terminal you'll need today.

---

### Launch Claude Code

```
claude
```

When it launches, it will ask you to log in. **Use the account you created with the referral link.** Choose "Log in with your Claude account" and follow the browser prompt.

Once you're in, try saying:

```
Hi! What can you do?
```

If Claude responds, you're ready to go.

---

### Create Your CLAUDE.md

A **CLAUDE.md** is a job description for Claude. Every time Claude starts working in your folder, it reads this file first. It tells Claude who you are, what you do, and how it should help you.

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

### Discover and Build Your Skills

This is the main event. Paste this prompt into Claude Code:

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

Claude will walk you through it interactively. Just answer its questions honestly about your work.

**Here are examples of what different roles might end up building:**

**Product Manager:**
- `/analyze-call` — paste a call transcript, get: key pain points, feature requests, sentiment, and next steps
- `/prioritize-features` — paste a list of feature requests, get: prioritized list with impact/effort scoring
- `/write-prd` — describe a feature, get: a structured PRD draft

**Sales:**
- `/validate-lead` — paste a company name + details, get: ICP fit score with reasons (good fit / bad fit / needs more info)
- `/cold-email` — paste company info, get: personalized outreach email under 150 words
- `/prep-call` — paste company info before a sales call, get: talking points, likely objections, questions to ask

**Marketing:**
- `/ad-copy` — describe your angle and audience, get: 3-4 ad copy variations with headlines, primary text, descriptions
- `/blog-draft` — paste an outline or topic, get: full blog draft with SEO structure
- `/social-post` — paste a company update, get: LinkedIn + Twitter variations

**Ops / PM:**
- `/status-update` — paste rough notes, get: professional stakeholder email
- `/summarize-notes` — paste meeting notes, get: summary + action items + decisions
- `/weekly-report` — paste bullet points, get: clean formatted report

---

### Test Your Skills with Sample Files

We've included sample files in the `samples/` folder of this repo for you to test with:

| Folder | File | What it is | Try with |
|--------|------|-----------|----------|
| `samples/product/` | `call_transcript.md` | A product discovery call transcript | `/analyze-call` |
| `samples/product/` | `feature_requests.md` | A log of 10 feature requests | `/prioritize-features` |
| `samples/sales/` | `icp_definition.md` | An Ideal Customer Profile document | `/validate-lead` |
| `samples/sales/` | `company_list.csv` | 20 companies to validate against ICP | `/validate-lead` |
| `samples/marketing/` | `ad_brief.md` | An ad campaign brain dump | `/ad-copy` |
| `samples/marketing/` | `blog_outline.md` | A blog content outline | `/blog-draft` |

To use them, copy the sample files into your `my-agent` folder and tell Claude:

```
Read the file call_transcript.md and analyze it using /analyze-call
```

Or simply paste the contents of any file directly into Claude Code.

---

## Power Features

These are the features that make Claude Code more than just a chatbot.

### Paste Images and Screenshots
You can paste images directly into Claude Code. Use cases:
- Paste a screenshot of a spreadsheet → "Extract this data into a table"
- Paste a competitor's ad → "Write 3 ad variations inspired by this"
- Paste a whiteboard photo → "Turn these notes into action items"

### Plan Mode
For bigger tasks, ask Claude to plan before doing anything:
```
/plan
```
Then describe what you want. Claude will outline the steps and ask for your approval before executing. Like asking your intern to outline their approach before starting work.

### Skip Permission Prompts
By default, Claude asks your permission before every file read/write. For trusted workflows:
- Press **Shift + Tab** to toggle between permission modes
- Choose "Allow all for this session" when you trust what it's doing

### Browse Your Skills
Type `/` to see all your saved skills. You can invoke any of them instantly.

### Read Any File
Drop any file into your folder and ask Claude about it:
```
Read report.csv and tell me the top 5 trends
```
Works with CSV, PDF, text, markdown, images, and more.

---

## Making Your Agent Smarter Over Time

### The Feedback Loop

The real power isn't the first output — it's that **your agent gets better every time you use it.**

**Step 1: Run a skill**
```
/cold-email
```

**Step 2: Look at the output — what's not right?**
Maybe it's too long, too formal, missing a CTA.

**Step 3: Give feedback with --improve**
```
/cold-email --improve "keep it under 100 words and always end with a question, not a statement"
```

**Step 4: Run it again — it's better now. Permanently.**
The skill file is updated. Every future run uses your feedback.

### Memory

Ask Claude to remember things that apply across ALL your conversations:
```
Remember that I prefer bullet points over paragraphs
Remember that when I say "client" I mean enterprise customers, not individual users
Remember that all my reports should use INR, not USD
```

These persist even when you start a new conversation.

### Update CLAUDE.md Over Time

Your CLAUDE.md should evolve as you use Claude Code more. If Claude consistently:
- Gets your tone wrong → add tone guidance to CLAUDE.md
- Misunderstands your domain terms → add a glossary section
- Formats things differently than you want → add formatting preferences

Just tell Claude:
```
Update the CLAUDE.md to mention that all my deliverables should use the company template format with headers in sentence case
```

### The Cycle
1. Use your skills daily
2. Notice when output isn't quite right
3. Use `--improve` to fix it
4. Update CLAUDE.md for broader preferences
5. Over time, your agent becomes an expert at YOUR specific work

---

## Git Setup (Version Control for Your Agent)

Now that you have a working agent with CLAUDE.md and skills, let's save it properly with Git. Think of Git as **"save points" for your project** — you can always go back to a previous version.

### Install Git

**Mac:**
```
xcode-select --install
```
A popup will appear — click "Install" and wait.

**Windows:**
Go to **https://git-scm.com/download/win** and run the installer (click Next through everything).

### Set Up Git in Your Project

```
git init
```
> This turns your folder into a Git project.

```
git add .
```
> This stages all your files (CLAUDE.md, skills, samples).

```
git commit -m "Initial setup: CLAUDE.md and skills"
```
> This saves a snapshot. You can always come back to this point.

### Why Git Matters
- Your CLAUDE.md and skills are valuable — don't lose them
- If you break something, you can undo it: `git checkout .`
- You can share your setup with teammates by pushing to GitHub
- Claude Code works even better in Git repos — it can see your history and understand your project

---

## Troubleshooting

### "command not found: npm"
Node.js isn't installed. Go back to the pre-work steps and install from https://nodejs.org

### "command not found: claude"
Claude Code isn't installed. Run:
```
npm install -g @anthropic-ai/claude-code
```

### Login isn't working
- Make sure you signed up using the referral link: https://claude.ai/referral/I6jwoLOL1A
- Try opening https://claude.ai in your browser first and logging in there
- Then come back to terminal and run `claude` again

### Claude is slow or not responding
- Check your internet connection
- Try `/clear` to start a fresh conversation
- Close and reopen terminal, then run `claude` again

### "Permission denied" on Mac
Try:
```
sudo npm install -g @anthropic-ai/claude-code
```
It will ask for your computer password (you won't see characters as you type — that's normal).

### Skills aren't showing up
- Make sure you're in the right folder: `cd my-agent`
- Type `/` to see all available skills
- If nothing shows, ask Claude: "List all the skill files in this project"

---

## What's Next?

You now have a personal AI agent tailored to YOUR work. Here's how to keep going:

1. **Use it daily** — the more you use it, the better it gets
2. **Build more skills** — any repetitive task can become a `/skill-name`
3. **Keep improving** — use `--improve` whenever output isn't perfect
4. **Drop files in your folder** — Claude can read and work with any document
5. **Share with teammates** — your skill files can be copied to anyone's setup
6. **Explore the docs** — https://docs.anthropic.com/en/docs/claude-code

Welcome to the future of work.

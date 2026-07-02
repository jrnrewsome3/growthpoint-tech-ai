# GitHub: The Swiss Army Knife of AI Work
## A Non-Developer's Guide to Using GitHub for Way More Than Code

**Module:** LifeQuest AI Curriculum | **Level:** Beginner-Intermediate  
**By:** Roger Newsome (JRN3) | **Date:** July 2026

---

## Why This Exists

Most people think GitHub is just for programmers storing code. That's like saying a Swiss Army knife is just a blade. In this module, you'll learn how to use GitHub as a **universal hub** for:

- Hosting free websites
- Storing and versioning documents
- Collaborating without email attachments
- Running AI automations
- Sharing training materials
- Backup and disaster recovery
- Publishing a personal brand

---

## LESSON  0: HOW TO MAKE A COMMIT (The Absolute Basics)

**The Problem:** Everyone says "just commit it" but nobody explains what that actually means or how to do it.

**What "Commit" Means:** A commit is a snapshot of your files at a specific moment, saved with a note explaining what changed. Think of it like saving a version of a Word document with a descriptive filename, except GitHub remembers every version forever.

### Method 1: In Your Browser (Easiest - No Tools Needed)

1. Go to your repo on github.com
2. Click the file you want to change
3. Click the pencil icon (top right of the file view)
4. Make your edits in the text box
5. Scroll down to "Commit changes..."
6. Write a short message describing what you changed (e.g., "Fix typo in Lesson 3")
7. Select "Commit directly to the main branch"
8. Click the green **Commit changes** button

Done. Your change is saved and tracked.

### Method 2: Using VS Code (What Roger Actually Does)

1. Open VS Code with your project folder
2. Make your edits to any file
3. Look at the left sidebar - click the **Source Control** icon (it looks like a branch)
4. You'll see your changed files listed under "Changes"
5. Hover over a file and click the **+** to "stage" it (tell GitHub you want to save this file)
6. Or click the **+** next to "Changes" to stage ALL files at once
7. Type a message in the box at the top (e.g., "Add new training module")
8. Click the **Commit** button
9. Click **Sync Changes** (or the icon with arrows) to push to GitHub

### Method 3: Using the Terminal (Power User)

```bash
# Step 1: Check what changed
git status

# Step 2: Add the files you want to save
git add filename.txt        # one file
git add .                    # all files

# Step 3: Save the snapshot with a message
git commit -m "Describe what you changed"

# Step 4: Send it to GitHub
git push origin main
```

### How to Write a Good Commit Message

| Bad Message | Good Message | Why |
|-------------|-------------|-----|
| "update" | "Add section on Docker containers to cheat sheet" | Tells you WHAT changed |
| "fix stuff" | "Fix broken table formatting in gotchas section" | Tells you WHERE and WHAT |
| "final" | "Add print-friendly CSS to HTML cheat sheet" | Tells you the real change |
| "asdf" | "Update OpenClaw token config after conflict" | Professional and searchable |

**Rule of thumb:** If you can't understand what changed by reading the message 6 months later, rewrite it.

---

## Lesson 1: GitHub Is a Free File Cabinet That Remembers Everything

**The Problem:** You have files everywhere - Desktop, Downloads, Google Drive, Dropbox, email attachments, USB sticks. You edit a document, save it as "FINAL_v2_ACTUALLY_FINAL.docx," and nobody knows which version is real.

**The GitHub Way:** Every change is tracked. Every version is saved. You can see WHO changed WHAT and WHEN. You can rewind to any point in time.

### What You'll Do
1. Create a repository (repo = digital folder)
2. Upload files via drag-and-drop or VS Code
3. Make a change and "commit" it (save a snapshot with a note)
4. Look at the history and see your past self

### Real-World Example
Roger stores his LifeQuest AI curriculum, GrowthPoint TechAI prompt libraries, website source code, and even this training guide in GitHub. One place. Searchable. Forever.

---

## Lesson 2: GitHub Pages = Free Website Hosting

**The Problem:** You want a website but don't want to pay $20/month for hosting or learn complex server management.

**The GitHub Way:** GitHub Pages hosts your website for free. Just HTML, CSS, and JavaScript files in a repo, and GitHub serves them to the world at `yourname.github.io`.

### What You'll Do
1. Create a repo named `yourname.github.io`
2. Add an `index.html` file
3. Go to Settings > Pages > Enable
4. Your site is live in 60 seconds

### Pro Moves
- Connect your own domain (lifequestai.com) via Cloudflare or Hostinger DNS
- Use a static site generator (Jekyll, Hugo) for blogs
- Deploy from VS Code with one click using GitHub + Vercel

### Real-World Example
Roger's LifeQuest AI site and GrowthPoint TechAI landing page are both built locally in VS Code, pushed to GitHub, and deployed via GitHub Pages + Cloudflare. Total cost: $0 for hosting. Domain: $18/year.

---

## Lesson 3: GitHub Issues = Your Public To-Do List

**The Problem:** You have ideas, bugs, tasks, and feedback scattered across sticky notes, emails, text messages, and napkins.

**The GitHub Way:** Issues are trackable tasks with labels, assignees, milestones, and comments. They're public (or private), searchable, and linkable. You can even close them from your commit messages.

### What You'll Do
1. Open the Issues tab in any repo
2. Create an issue: "Add video module to Week 3"
3. Label it: `enhancement`, `training`, `urgent`
4. Assign it to yourself or a collaborator
5. When done, commit with message "Fixes #42" and it auto-closes

### Real-World Example
Roger tracks all his venture ideas as GitHub Issues across his repos. "Launch pain-point survey" is an open issue in the LifeQuestAI repo with a checklist and due date.

---

## Lesson 4: GitHub Actions = Robots That Work While You Sleep

**The Problem:** You manually check things, run tests, deploy updates, or send reports. It's repetitive and you forget.

**The GitHub Way:** Actions are automated workflows that trigger on events (push, schedule, pull request). They can test code, deploy websites, send emails, run AI models, or anything a computer can do.

### What You'll Do
1. Create `.github/workflows/hello-world.yml`
2. Define a trigger: `on: [push]` or `on: schedule` (cron)
3. Define steps: checkout code, run a script, deploy
4. Push the file and watch the robot work

### Real-World Example
Roger uses GitHub Actions to auto-deploy his website every time he pushes a change. No manual FTP. No "oops I forgot to upload the new file." Push to Live.

---

## Lesson 5: GitHub Copilot = AI Pair Programmer

**The Problem:** You're learning to code or building a website and you get stuck on syntax. You don't want to keep asking AI for every line.

**The GitHub Way:** Copilot lives inside VS Code and suggests code as you type. It's like having a junior developer who never sleeps and knows every programming language.

### What You'll Do
1. Install GitHub Copilot extension in VS Code
2. Start typing HTML, CSS, JavaScript, Python, or even plain English comments
3. Copilot suggests completions
4. Press Tab to accept, or keep typing to refine

### Real-World Example
Roger built his entire LifeQuest AI curriculum website using Copilot in VS Code. He describes what he wants in comments, and Copilot writes the HTML/CSS skeleton.

---

## Lesson 6: GitHub Gists = Shareable Code Snippets

**The Problem:** You have a useful script, config file, or note you want to share quickly. Creating a whole repo feels like overkill.

**The GitHub Way:** Gists are mini-repositories for single files or small collections. Each gist gets a unique URL you can share, embed, or bookmark.

### What You'll Do
1. Go to gist.github.com
2. Paste your content (a bash alias collection, a config file, a recipe)
3. Set public or secret
4. Share the URL

### Real-World Example
Roger keeps his "Top 50 Terminal Commands" as a public gist. Students bookmark it. Other developers fork it. It becomes a living document.

---

## Lesson 7: GitHub Projects = Kanban Board for Anything

**The Problem:** You use Trello, Asana, or a whiteboard to track work, but it's disconnected from where your actual work lives.

**The GitHub Way:** Projects are built-in Kanban boards tied directly to your repos, issues, and pull requests. One view of everything.

### What You'll Do
1. Go to the Projects tab in a repo or organization
2. Create a board with columns: Backlog, In Progress, Review, Done
3. Drag issues and pull requests across columns
4. Add custom fields: priority, effort, deadline

### Real-World Example
Roger runs his entire LifeQuest AI content pipeline through a GitHub Project. Columns: Idea > Outline > Draft > Edit > Publish. Cards move left to right. No tool switching.

---

## Lesson 8: GitHub as Backup & Disaster Recovery

**The Problem:** Your computer crashes. Your hard drive dies. Your house floods. Your work is gone.

**The GitHub Way:** Every file you push to GitHub exists in at least three places: your local machine, GitHub's servers, and (if you clone to another device) your other machine. It's automatic distributed backup.

### What You'll Do
1. Push your important docs, photos, configs to a private repo
2. Clone the repo to a second machine (or your phone via Working Copy)
3. Sleep soundly

### Real-World Example
Roger's .zshrc, SSH config, VS Code settings, and even his Obsidian vault backup script all live in a private dotfiles repo. New machine setup: clone, symlink, done.

---

## Lesson 9: GitHub for Collaboration Without Chaos

**The Problem:** You email a document to five people. Everyone edits it. Now you have six versions and a headache.

**The GitHub Way:** One file. Many contributors. Changes are proposed as "pull requests" (suggested edits) that you review and approve. No version conflicts. No lost work.

### What You'll Do
1. Add a collaborator to your repo (Settings > Collaborators)
2. They make changes in a branch and open a pull request
3. You review the diff (exactly what changed)
4. Approve, request changes, or merge

### Real-World Example
Roger and his daughter Loughlin co-write curriculum modules. She writes in a branch, opens a PR, Roger reviews and merges. No "Track Changes" mess.

---

## Lesson 10: GitHub as Your Public Resume & Brand

**The Problem:** You tell people you're learning AI, building projects, and writing content. They ask "show me." You have nothing to point to.

**The GitHub Way:** Your GitHub profile is a living portfolio. Green contribution graph = consistency. Pinned repos = your best work. README profile = your elevator pitch.

### What You'll Do
1. Create a repo named exactly your username (e.g., `jrnrewsome3/jrnrewsome3`)
2. Add a README.md with your bio, links, and featured projects
3. Pin your best repos to your profile
4. Keep committing = keep the graph green

### Real-World Example
Roger's GitHub profile README links to LifeQuest AI, GrowthPoint TechAI, AskPops.ai, and his AI literacy curriculum. One URL tells his whole story.

---

## Quick Reference: GitHub for Non-Developers

| I Want To... | GitHub Feature | Time to Learn |
|--------------|---------------|---------------|
| Store files with version history | Repository + Commits | 15 min |
| Host a free website | GitHub Pages | 20 min |
| Track tasks | Issues + Projects | 20 min |
| Automate repetitive work | GitHub Actions | 1 hour |
| Get AI code help | GitHub Copilot | 10 min |
| Share a snippet quickly | Gists | 5 min |
| Collaborate on documents | Pull Requests | 30 min |
| Back up my life | Private repos | 15 min |
| Show my work to the world | Profile README | 30 min |
| Connect everything to everything | GitHub API + webhooks | 2+ hours |

---

## Your First 48 Hours

**Day 1 (30 minutes):**
1. Sign up at github.com
2. Create a repo named `your-username` (for profile README)
3. Write a simple README about who you are and what you're building
4. Create a second repo called `my-first-website`
5. Add an `index.html` file with "Hello World"

**Day 2 (30 minutes):**
1. Enable GitHub Pages on `my-first-website`
2. Open an Issue: "Make website prettier"
3. Make a small edit to `index.html`, commit it
4. Visit your live site at `https://your-username.github.io/my-first-website`
5. Celebrate. You just published to the web.

---

## Advanced: The GitHub Ecosystem for AI Builders

| Tool | What It Does | How Roger Uses It |
|------|-------------|-------------------|
| **GitHub + VS Code + Copilot** | Local dev with AI assistance | Builds all his sites and apps |
| **GitHub + Vercel** | Auto-deploy from push | `vercel --prod` linked to repo |
| **GitHub + Ollama** | Local LLM model storage | Pulls models, tracks experiments |
| **GitHub + Docker** | Containerized apps | OpenClaw deployment configs |
| **GitHub + GitHub CLI** | Terminal control of repos | `gh repo create`, `gh pr create` |
| **GitHub + Notion/Obsidian** | Documentation sync | Curriculum drafts > GitHub > Publish |

---

## Call to Action

1. **Create your GitHub account today** (if you haven't)
2. **Make your profile README repo** - tell your story
3. **Upload one project or document** - anything
4. **Enable GitHub Pages** on one repo - see your name on the internet
5. **Open your first Issue** - track one real task
6. **Install GitHub Copilot** in VS Code - feel the AI accelerate you

GitHub is not just for developers. It's for **anyone who creates things and wants those things to last**.

---

*Module built for LifeQuest AI Curriculum | Roger Newsome (JRN3) | July 2026*
# miramar-labs-org.github.io

Miramar Labs blog — published at [miramar-labs-org.github.io](https://miramar-labs-org.github.io).

Built with Jekyll / Minima. Draft posts live as open PRs on `draft-<name>` branches; merging to `main` publishes them (~60s GitHub Pages rebuild).

---

## Editorial workflow

### Setup (once)

Start the SSH tunnel with port 4001 included:

```sh
ssh -L 4001:localhost:4001 \
    -L 8001:localhost:8001 \
    -L 8888:localhost:8888 \
    -L 5000:localhost:5000 \
    -L 8080:localhost:8080 \
    -L 8082:localhost:8082 \
    -L 8890:localhost:8890 \
    -L 11434:localhost:11434 \
    aaron@spark-79b7.local
```

Start Jekyll on the DGX if it isn't already running:

```sh
ssh aaron@spark-79b7.local
cd ~/git-miramar-labs-org/miramar-labs-org.github.io
git pull
nohup bundle exec jekyll serve --host 0.0.0.0 --port 4001 > /tmp/jekyll.log 2>&1 &
```

Then open [http://localhost:4001](http://localhost:4001) in your browser.

> **Note:** port 4000 is permanently occupied by the NoMachine daemon (`nxd`) on DGX OS. Always use 4001.

### Writing a new post

**Step 1 — Create the project** *(you are on `main` in the blog repo)*

Run the **Create Project** workflow. It automatically:
- Creates the project repo under `miramar-labs-org`
- Opens a draft PR on this blog repo with a stub post on `draft-<project-name>`
- Checks out `draft-<project-name>` on the DGX so Jekyll picks it up immediately

**Step 2 — Edit the post** *(you are on `draft-<project-name>` in the blog repo on the DGX)*

Open `_posts/YYYY-MM-DD-<project-name>.markdown` in VS Code (via SSH remote or JupyterLab). Every save live-reloads at [http://localhost:4001](http://localhost:4001). Write freely — nothing is public yet.

**Step 3 — Save your progress** *(you are on `draft-<project-name>`)*

Commit and push to keep your work backed up on GitHub:

```sh
git add _posts/YYYY-MM-DD-<project-name>.markdown
git commit -m "draft: update clinical-ft-pipeline post"
git push
```

Or use VS Code's Source Control tab: stage the file → write a commit message → click **Commit** → click the sync button.

**Step 4 — Publish** *(you are on `draft-<project-name>`)*

When the post is ready to go live:

- Open the draft PR on GitHub (`github.com/miramar-labs-org/miramar-labs-org.github.io/pulls`)
- Merge it — GitHub Pages rebuilds in ~60s and the post is public at `miramar-labs-org.github.io`

Or use the [GitHub Pull Requests](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) VS Code extension to merge without leaving the editor.

**Step 5 — Switch back** *(you are on `draft-<project-name>` on the DGX)*

Return Jekyll to serving the live site:

```sh
git checkout main && git pull
```

---

### Editing a live post

*(You are on `main` in the blog repo)*

1. Create a new branch: `git checkout -b edit/<post-name>`
2. Edit `_posts/YYYY-MM-DD-<post-name>.markdown` — preview at [http://localhost:4001](http://localhost:4001)
3. Commit, push, open a PR, merge — Pages rebuilds in ~60s

---

### Multiple drafts

*(You are on one draft branch on the DGX; you want to preview a different one)*

Jekyll serves whatever branch is checked out on the DGX. Switch to preview another draft:

```sh
# currently on draft-project-a
git checkout draft-project-b
# preview at http://localhost:4001 — now shows project-b's draft
git checkout draft-project-a  # switch back when done
```

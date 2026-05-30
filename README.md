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

1. Run the **Create Project** workflow — it auto-opens a draft PR with a stub post on `draft-<project-name>`
2. On the DGX: `git fetch && git checkout draft-<project-name>`
3. Jekyll live-reloads — edit `_posts/YYYY-MM-DD-<name>.markdown` and preview at `http://localhost:4001`
4. Commit and push edits to the draft branch
5. When ready to publish, merge the PR on GitHub — post goes live in ~60s
6. Switch Jekyll back to main: `git checkout main`

### Editing a live post

1. `git checkout main && git pull`
2. Edit the post file, commit, push on a new branch, open a PR
3. Merge the PR — Pages rebuilds in ~60s

### Multiple drafts

Jekyll serves whichever branch is checked out on the DGX. Switch branches to preview a different draft:

```sh
git checkout draft-<other-project>
# preview at http://localhost:4001
git checkout main  # or draft-<current> when done
```

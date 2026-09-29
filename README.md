# DSA Tracker

A small, single-file web app I built to keep myself honest while learning Data Structures & Algorithms in Python.

I kept starting DSA prep, losing track of what I'd covered, and quietly dropping it after a few weeks. So I made a tracker around a fixed 2-year plan: every topic has a target number of days and a target number of questions, and I can see at a glance where I'm ahead or behind. No framework, no build step, no backend to host. It's just one `index.html`.

## What it does

- **2-year roadmap, 5 phases, 28 topics.** From Recursion and Hashmaps up to Segment Trees and timed contests. Each topic has its own day target and question target.
- **Day and question counters.** Tap `+` when I practice for the day, add a question when I solve one. If I go over the target, it shows the extra instead of pretending I'm done.
- **Streaks and a heatmap.** Current streak, best streak, and a 12-week activity grid, so skipping days is visible.
- **Per-question notes.** For each solved question I save the name, a link, and my approach or code.
- **Google Drive sync.** Notes and attached files upload to a Drive folder for that topic, so my notes live somewhere permanent and not just in the browser.
- **Backup and restore.** Export everything as JSON, or as text laid out as `DSA / topic / question.md`, and restore it on another browser.
- **Works on my phone.** Layout is responsive, and the dark red theme is easy on the eyes at night.

## The plan

| Phase | Focus | Topics |
|-------|-------|--------|
| 1 | Algorithm Patterns | Recursion, Hashmap/HashSet, Prefix Sum, Two Pointers, Sliding Window, Binary Search, Sorting + Intervals, Backtracking, Greedy, Bit Manipulation |
| 2 | Data Structures | Linked List, Stack/Queue/Monotonic, Trees + BST, Heap, Trie, Graphs, Shortest Paths + MST |
| 3 | Dynamic Programming | 1D, 2D/Grid, Knapsack, String DP, Trees/Bitmask/Intervals |
| 4 | Advanced | Segment/Fenwick Tree, String Algorithms, Math + Number Theory, Advanced Graphs |
| 5 | Mastery | Mixed Revision, Timed Practice + Contests |

That works out to roughly 100 weeks and about 860 questions in total. The numbers per topic are just what I think is reasonable, and you can change them in the `T` array in the script.

## Running it

There's nothing to install. Download or clone the repo and open `index.html` in a browser.

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
# then just open index.html
```

It also works on GitHub Pages if you want it on your phone: *Settings → Pages → deploy from the `main` branch*.

## Where the data lives

Progress is saved in the browser's `localStorage`, so it stays on your device and is never sent anywhere by default. The catch is that clearing site data wipes it, which is why I added the JSON backup. Use **Backup (JSON)** now and then.

## Setting up Drive uploads (optional)

The Drive sync goes through a small Google Apps Script web app that I deployed myself, so you'll need your own if you want it:

1. Create one Drive folder per topic (28 in total).
2. Write an Apps Script `doPost` that checks a shared secret, then saves the uploaded file into the folder ID it receives.
3. Deploy it as a web app.
4. In `index.html`, replace `API` with your deployment URL and fill the `FID` array with your folder IDs, in the same order as the topics.
5. The first upload asks for your passcode and remembers it in the browser.

If you skip this, everything else still works. Questions will just show a warning icon instead of the cloud icon.

## Built with

Vanilla HTML, CSS and JavaScript. No dependencies. The whole thing is one file, which is deliberate: I wanted something I could open anywhere and edit in a minute.

## Things I might add

- Spaced-repetition reminders for old questions
- Difficulty tags (Easy/Medium/Hard) per question
- Charts for progress over time

## License

MIT. Use it, fork it, and change the plan to fit your own prep.

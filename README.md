# Concordantia — a verified library of classic Christian theology for Claude Desktop

Concordantia adds a 64-million-word library of classical Christian theology
to [Claude Desktop](https://claude.ai/download) — the early church fathers,
medieval teachers, the Reformers, and their heirs, 262 works in all — and
**mechanically checks every quotation against the actual source text before
the words reach you.** When Claude answers, each quote carries its author,
work, and location, and every answer ends with a Sources list whose links
open the exact passage.

This guide assumes no technical background. If you can install an app, you
can do this. Budget about 30 minutes the first time, most of it downloads.

---

## What you will need

- A **Mac** or **Windows 10/11 PC** (64-bit Intel/AMD).
- Internet access for the downloads (a good chunk of it is one-time).
- A **Claude account** — free to create at [claude.ai](https://claude.ai).
  The free plan works; paid plans simply raise Claude's daily usage limits.
- That's all. No programming, no terminal, nothing to configure.

> **Why two pieces?** Claude learns a new library through a *connector*
> (the file that carries the search engine), and it learns *how to study
> well* through a *skill* (a short instruction file). You'll install one of
> each below. Together they make Claude do what a careful researcher does:
> search the library first, read the passage, and verify the quote before
> writing it down.

---

## Step 1 — Install Claude Desktop

1. Go to **[claude.ai/download](https://claude.ai/download)**.
2. Download the version for your computer (macOS or Windows) and install it
   the way you install any app: open the downloaded file and follow the
   prompts. On a Mac, drag Claude into your Applications folder if asked.
3. Open Claude and **sign in** (or create a free account).

Note: this is the **desktop app**, not the website in your browser. The
library works only inside the desktop app.

## Step 2 — Download your two files

Both files are on this project's **Releases** page — most likely the page
you just came from ([concordantia.net](https://concordantia.net) lands
there). A release page has reading material at the top; **the downloadable
files sit at the very bottom, under a heading called Assets.** Scroll down
and download the two files that match your computer:

| Your computer | The connector file | Size |
|---|---|---|
| Mac, 2020 or later (chip listed as *Apple M1, M2, M3, M4…*) | `Concordantia-for-Claude-darwin-arm64.mcpb` | ~23 MB |
| Mac, older (chip listed as *Intel*) | `Concordantia-for-Claude-darwin-x64.mcpb` | ~23 MB |
| Windows 10 or 11 PC | `Concordantia-for-Claude-win32-x64.mcpb` | ~21 MB |
| **Everyone** — the study skill | `concordantia-study-skill.zip` | tiny |

**Not sure which Mac you have?** Click the Apple logo at the top-left of
your screen and choose **About This Mac**, then look at the **Chip** row: if it
says *Apple M1/M2/M3/M4*, use the **arm64** file; if it says *Intel*, use
the **x64** file. Nearly every Windows PC from the last decade takes the
**win32-x64** file.

Leave the files in your Downloads folder for the next step.

## Step 3 — Install the library (double-click)

**Double-click the `.mcpb` file you downloaded.** Claude Desktop opens with
a small window describing "Concordantia" — click **Install**. That's the
whole installation: Claude now carries the library.

## Step 4 — Teach Claude the study method (2 minutes)

1. In Claude, open **Settings** (the gear icon) and find **Capabilities**.
2. Turn **on "Code execution and file creation."** Claude requires this
   before it will accept skills; nothing else changes.
3. In Settings, scroll to **Skills** and click **Upload skill** (you may
   find it under a "Customize" heading). Choose the
   `concordantia-study-skill.zip` file you downloaded.
4. In the Skills list, make sure **concordantia-study** is toggled **ON**.

Now **start a new chat** — Claude picks up new skills in fresh chats. Invoke
the study method by typing **`/concordantia-study`** followed by your
question; that is the reliable way to begin.

---

## A word about the security warning (please read once)

Depending on your system, you may see a warning like *"…can't be opened
because Apple cannot check it for malicious software"* (Mac) or *"Windows
protected your PC"* (Windows). **This is expected today, and here is the
honest story behind it.**

Apple and Microsoft show that warning for any program whose maker has not
purchased an annual code-signing certificate — a receipt that tells your
computer who published the file. Concordantia is distributed free by
Resurrection Publishing, and the signing paperwork is not yet in place. The
warning means *"I don't recognize the publisher,"* not *"this file is
dangerous."* You know exactly where this file came from: the official
release page of this project. (If you received a copy from anywhere else,
delete it and download from here.)

**Windows:** on the blue warning screen, click **More info**, then **Run
anyway**. You'll do this once per installation.

**Mac:** installing the connector normally needs no extra step. If, after
installing, the Concordantia tools never appear in Claude, the usual reason
is Apple's security flag on the downloaded helper program. Do this one time:

1. Open **Terminal**: press `Cmd + Space`, type `Terminal`, press Enter.
2. Copy the line below, paste it into Terminal, press `Enter`:
   ```
   xattr -dr com.apple.quarantine "$HOME/Library/Application Support/Claude/Claude Extensions/local.mcpb.flaremark.concordantia"
   ```
3. If Terminal says the folder doesn't exist, list what's there and repeat
   with the folder name that contains `concordantia`:
   ```
   ls "$HOME/Library/Application Support/Claude/Claude Extensions"
   ```
4. Quit Claude fully (press `Cmd + Q` while Claude is frontmost, or
   right-click its Dock icon → Quit) and open it again.

This one command removes the quarantine flag from this one installed app.
It changes nothing else on your Mac.

<details>
<summary><b>Optional:</b> check the file's fingerprint before installing</summary>

Every release publishes a SHA-256 fingerprint for each file (the
`.sha256` files). To compare yours — optional, but it proves your download
arrived exactly as published:

- **Mac** — in Terminal: `shasum -a 256 ~/Downloads/Concordantia-for-Claude-darwin-arm64.mcpb`
  (use your actual filename), then compare the long code with the matching
  `.sha256` file.
- **Windows** — in the Start menu, open **Command Prompt** and run:
  `certutil -hashfile "%USERPROFILE%\Downloads\Concordantia-for-Claude-win32-x64.mcpb" SHA256`

</details>

---

## First use: one big download, then everything is local

Ask your first question. Claude will quietly fetch the library itself —
**about 1 GB, once**, into a folder Claude manages (you never choose a
path). On a decent connection this takes a few minutes; do it while you're
on good Wi-Fi. Every later question runs **entirely on your own computer** —
instant, and private: your searches and sermon notes never leave the
machine.

---

## Try it: questions that show what this does

Start a fresh chat, type **`/concordantia-study`**, then your question —
like this:

> `/concordantia-study` How has the doctrine of the Trinity developed in church history?

Claude will study the library on its own — searching several angles,
fetching the passages, verifying the quotes — and answer with (Author,
Work, section) beside each claim. (A plain question often works too, since
the skill teaches Claude when to reach for the library — but the slash
form makes it certain.)

**How doctrines developed — the long story, from the sources**

- *"How has the doctrine of the Trinity developed in church history?"*
- *"How did Christology develop from 100 to 500 AD?"*
- *"What is the history of the doctrine of original sin?"*
- *"How did the Filioque controversy develop, and why did East and West part ways?"*

**Anchored in a specific passage or book of the Bible**

- *"What do the commentators say Esther 9 teaches about God's providence?"*
- *"How has John 6:35 been read in the church's teaching on the Lord's Supper?"*
- *"How did Athanasius use Scripture against the Arians?"*
- *"What did Augustine teach about grace in his writings against Pelagius?"*

**For sermon prep and pastoral care**

- *"How does a Christian's daily work relate to their salvation? What did Luther and Calvin say about calling?"*
- *"What has the church taught through history about whether war can be just?"*
- *"How did the Reformers and the Roman Catholic Church differ on justification?"*
- *"What did the first Christians believe about baptism?"*

Each answer ends with a **Sources list**. Every entry names the work and
carries a link; click one and your browser opens the **exact passage**,
with the quoted words highlighted, so you can read it in context yourself —
the pastor's habit of checking the reference, made one click easy.

---

## What a good answer looks like

Claude's answers will quote sparingly and attribute precisely, in a shape
like this (from this very library, and verified):

> …on daily work, Calvin will not let the cobbler think his bench is beneath
> God's notice: "in following your proper calling, no work will be so mean
> and sordid."
>
> **Sources**
> - John Calvin, *Institutes of the Christian Religion* (calvin-institutes 1796683–1801239) — http://127.0.0.1:8765/passage/calvin-institutes/1796683-1801239
> - James Arminius, *Works, Vol. 2*, "Disputation XLII: On the Vocation of Sinful Men" (arminius-works-vol2 182337–186991)

Two habits make it work better for you:

- **Ask for the tradition when it matters.** "…and show me where Reformed,
  Lutheran, Arminian, and Roman Catholic teachers disagree" turns a summary
  into a map of the debate. The disagreements are part of the answer.
- **Expect honesty about limits.** If the library lacks a source, Claude is
  instructed to say so plainly rather than fake a citation — and every
  quotation you see has already passed the mechanical check.

---

## What's on the shelf

- **Scripture** — the King James Bible, the Septuagint, and the Greek New
  Testament.
- **The early church** — the Ante-Nicene and Nicene sets: Irenaeus,
  Tertullian, Athanasius, Basil, the two Gregories, Chrysostom, Jerome,
  Augustine (Confessions, the anti-Pelagian works, and more), Leo the
  Great, Gregory the Great.
- **Medieval** — Anselm (*Proslogion* and *Cur Deus Homo*), Peter Lombard's
  *Sentences*, Thomas Aquinas' *Summa Theologica*, Thomas à Kempis'
  *Imitation of Christ*.
- **Reformation** — Luther (Galatians commentary, *Bondage of the Will*,
  Small Catechism, Table Talk), Calvin (*Institutes* and commentaries),
  Zwingli, and the confessions: Augsburg, Formula of Concord, Belgic,
  Second London Baptist (1689).
- **Catholic and devotional voices** — Ignatius Loyola's *Spiritual
  Exercises*, Pascal's *Pensées*.
- **Post-Reformation** — Arminius, the Puritans (Baxter, Bunyan), Hodge,
  Witsius, and Schaff's *History of the Christian Church* and *Creeds of
  Christendom*.

An honest note: the collection **leans Reformation and Protestant**, with
the Catholic and Orthodox traditions present through the Fathers, the
medieval doctors, Ignatius, and Pascal — but selectively. Ask it to show
how the traditions differ; that contrast is part of what the library is
for.

---

## Care and feeding

- **Updating.** When a new release is announced, download the new `.mcpb`
  for your platform and double-click it — it installs over the old one.
  Your library and settings are kept.
- **Removing.** Claude Desktop → Settings → the extensions list →
  Concordantia → Remove. The skill can be toggled off or deleted in the
  same Settings, under Skills.
- **Privacy.** After the one-time download, searching, fetching, and
  verifying all run on your computer. Nothing is sent to any server by
  Concordantia.
- **Space.** Keep about 3 GB free; the library itself is ~1 GB.

## Troubleshooting

| Symptom | Fix |
|---|---|
| The Concordantia tools never appear | Quit Claude **fully** (Cmd+Q on Mac; right-click the tray icon → Quit on Windows) and reopen. Check Settings → Extensions shows Concordantia enabled. |
| Mac blocked the install (see the security section above) | Run the one-line `xattr` command above, then restart Claude. |
| Windows shows the blue "protected your PC" screen | **More info** → **Run anyway** — once per install. |
| Answers have no Sources list | Start a **new chat** and invoke the skill explicitly: type `/concordantia-study` + your question. Also confirm the *concordantia-study* skill is toggled ON in Settings → Skills. |
| A source link won't open | The passage reader lives inside the running app. It wakes with your next question — ask Claude anything, then click the link again. |
| Very slow or fails mid-download | The first ~1 GB fetch needs a stable connection; try again on better Wi-Fi. It starts over, then never downloads again. |
| Still stuck | Open an issue on this repository — describe your computer (Mac or Windows, roughly how old) and what you saw. |

---

*Concordantia is built and given away by Resurrection Publishing. The texts
in the library are public-domain or freely licensed; the tooling is MIT.
Version and release notes: see the Releases page.*
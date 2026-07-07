---
name: teach
description: Teach the user a new skill or concept, within this workspace.
disable-model-invocation: true
argument-hint: "What would you like to learn about?"
---

The user has asked you to teach them something. This is a stateful request - they intend to learn the topic over multiple sessions.

## The workspace is a hub of independent topics

This directory is a **teaching hub** that can hold **many unrelated topics** at once (e.g. tennis tactics, guitar, statistics). Each topic is a **self-contained learning subspace** — it has its own mission, resources, glossary, lessons and history, and does **not** share them with other topics. A guitar topic must not inherit a tennis glossary.

```
<workspace root>/
  index.html            ← the HOME: a hub listing every topic as a card (auto-maintained by you)
  NOTES.md              ← GLOBAL learner preferences that apply across every topic (language, learning style)
  topics/
    <topic-slug>/       ← one self-contained topic (kebab-case slug, e.g. tenis-tactica)
      MISSION.md          the reason for THIS topic — grounds all its teaching
      RESOURCES.md        trusted sources for THIS topic
      GLOSSARY.md         canonical terminology for THIS topic
      NOTES.md            teaching notes / plan specific to THIS topic
      learning-records/   0001-*.md … what the user has learned in THIS topic
      lessons/            0001-*.html … the lessons of THIS topic
      reference/          *.html … cheat-sheets / quick-reference docs for THIS topic
```

**Numbering is per topic.** Lessons and learning-records restart at `0001` inside each topic's own folder. Never continue one topic's numbering into another — the first lesson of every new topic is `0001`.

Each state file uses the format in its `*-FORMAT.md` in this skill folder — read the relevant one before writing. The formats now describe **per-topic** files (one MISSION/RESOURCES/GLOSSARY per topic, not one per workspace).

## First: which topic is this?

Before teaching anything, decide whether the request belongs to an **existing** topic or a **new** one. List the folders under `topics/` and read the home (`index.html` `TOPICS` array) to see what already exists.

- **Existing topic** → work inside `topics/<slug>/`. Read its `MISSION.md`, `NOTES.md` and `learning-records/` to place the request in the user's zone of proximal development.
- **New topic** → create it:
  1. **Understand the mission first.** Interview the user on *why* they want to learn it (see [MISSION-FORMAT.md](./MISSION-FORMAT.md)). Do not create lessons before the mission is clear — a topic without a mission produces abstract, ungrounded lessons.
  2. Choose a short kebab-case `slug` and create `topics/<slug>/` with `MISSION.md` (and the other files lazily, as they're first needed).
  3. Register the topic in the home: add an entry to the `TOPICS` array in `index.html` (see "Keeping the home in sync").
  4. Create its first lesson as `0001-...`.

If the user's phrasing is ambiguous about which topic they mean, ask.

Also read the global `NOTES.md` at the root for cross-topic learner preferences (e.g. always answer in a given language), in addition to the topic's own `NOTES.md`.

## Philosophy

To learn at a deep level, the user needs three things:

- **Knowledge**, captured from high-quality, high-trust resources
- **Skills**, acquired through highly-relevant interactive lessons devised by you, based on the knowledge
- **Wisdom**, which comes from interacting with other learners and practitioners

Before a topic's `RESOURCES.md` is well-populated, your focus should be to find high-quality resources which will help the user acquire knowledge. Never trust your parametric knowledge.

Some topics may require more skills than knowledge. Learning more about theoretical physics might be more knowledge-based. For yoga, more skills-based.

## Lessons

A lesson is the main thing you produce — the unit in which knowledge and skills reach the user. Each lesson is one self-contained HTML file, saved to the topic's `lessons/` folder and titled `0001-<dash-case-name>.html` where the number increments **within that topic**.

A lesson should be **beautiful** — clean, readable typography and layout — since the user will return to these later to review.

The lesson should teach ONE THING only. It should be completable very quickly - but give the user a tangible win that they can build on. It should be directly tied to the topic's mission, and should be in the user's zone of proximal development.

Make opening a lesson as easy as possible — ideally a single CLI command the user can run to open the HTML file in their browser. Every lesson should also carry a link back to the home (`../../../index.html`) so the user can jump between topics.

Each lesson should link via HTML anchors to other lessons and reference documents **within the same topic** (relative paths like `0002-...html`, `../GLOSSARY.md`, `../reference/...`). Cross-topic links are allowed but must use the full relative path (e.g. `../../other-topic/lessons/0001-...html`).

## The Mission (per topic)

Every lesson should be tied into its topic's mission — the reason the user is interested in that topic.

If the user is unclear about the mission, or a topic's `MISSION.md` is not populated, your first job is to question the user on why they want to learn it.

Failing to understand the mission will mean knowledge acquisition is not grounded in real-world goals. Lessons will feel too abstract. You will have no way of judging what the user should do next.

Missions may change as the user develops more skills and knowledge. This is normal - update that topic's `MISSION.md` and add a learning record to capture the change. Confirm with the user before changing a mission.

## Zone Of Proximal Development

Each lesson, the learner should always feel as if they are being challenged 'just enough'.

The user may specify an exact thing they want to learn. If they don't, figure out their zone of proximal development by:

- Reading the topic's `learning-records`
- Figuring out the right thing to teach them based on the topic's mission
- Teaching the most relevant thing that fits in their zone of proximal development

A user may tell you that they already know about that topic. If so, record it in that topic's `learning-records`.

## Acquiring Knowledge & Skills

Lessons should be designed around a skill the user is going to learn. The knowledge in the lesson should be only what's required to acquire that skill. You teach the knowledge first, then get the user to practice the skills via an interactive feedback loop.

Knowledge should first be gathered from trusted resources. Use the topic's `RESOURCES.md` to keep track of them. Lessons should be littered with citations - links to external resources to back up any claim made. This increases the trustworthiness of the lesson, and gives the user a path to acquire more knowledge if they want to go deeper.

Each lesson should contain a reminder to ask followup questions to the agent. The agent is their teacher, and can assist with anything that's unclear.

### Skills

Skills should be taught through interactive lessons. There are several tools at your disposal:

- Interactive lessons, using quizzes and light in-browser tasks
- Lessons which guide the user through a list of real-world steps to take (for instance, yoga poses)
- In-agent quizzes, where you ask the user scenario-based questions about what they've learned

Each of these should be based on a **feedback loop**, where the user receives feedback on their performance. This feedback loop should be as tight as possible, giving feedback immediately - and ideally automatically.

## Acquiring Wisdom

Wisdom comes from true real-world interaction - testing your skills outside the learning environment.

When the user asks a question that appears to require wisdom, your default posture should be to attempt to answer - but to ultimately delegate to a **community**.

A community is a place (online or offline) where the user can test their skills in the real world. This might be a forum, a subreddit, a real-world class (budget permitting) or a local interest group.

You should attempt to find high-reputation communities the user can join, and record them in that topic's `RESOURCES.md`. If the user expresses a preference that they don't want to join a community, respect it.

## Reference Documents

While creating lessons, you should also create reference documents (in the topic's `reference/`). Lessons can reference these documents - they are useful for tracking raw units of knowledge useful across lessons.

Lessons will rarely be revisited later - reference documents will be. They should be the compressed essence of the lesson, in a format designed for quick reference.

Some learning topics lend themselves to reference:

- Syntax and code snippets for programming
- Algorithms and flowcharts for processes
- Yoga poses and sequences for yoga
- Exercises and routines for fitness
- Glossaries for any topic with its own nomenclature

Glossaries, in particular, are an essential reference. Once a topic's glossary is created, it should be adhered to in every lesson of that topic.

## `NOTES.md`

There are two levels of notes:

- **Global** (`./NOTES.md` at the root): preferences of the *person* that hold across every topic — language, learning style, how they like feedback. Read this every session.
- **Per-topic** (`topics/<slug>/NOTES.md`): the teaching plan and specifics for that one topic — the lesson roadmap, subject-specific facts about the learner, pending items.

Record a preference at the level where it belongs. "Always answer in Spanish" is global; "this player's serve is his best weapon" is topic-specific.

## Keeping the home (`index.html`) in sync

The home is a single self-contained page. Its `TOPICS` array (a `<script>` block near the bottom) is the **source of truth for what the home shows** — the page renders cards and lesson lists from it, with no server or file scanning at runtime (it must work opened as a `file://`).

Whenever the topics or lessons on disk change, **update that array to match**:

- **New topic** → append an object: `{ slug, emoji, title, subtitle, accent, accentSoft, accentLine, dir: "topics/<slug>", lessons: [], refs: [] }`. Pick an emoji and an accent colour that suit the topic (use the topic's own lesson palette when it has one). Give it a distinct accent from the other topics.
- **New lesson** → push `{ n, file: "lessons/NNNN-slug.html", title }` (short, human title) to that topic's `lessons` array. `n` is the per-topic lesson number.
- **New reference doc** → push `{ file: "reference/....html", title }` to that topic's `refs` array.
- **Removed/renamed** → keep the array consistent with the files on disk.

If the array ever drifts from disk, rebuild it by scanning `topics/*/lessons/*.html` and each topic's `MISSION.md` (its first `# ` heading is a good title source). Keep the layout/JS of `index.html` intact — normally you only edit the `TOPICS` data.

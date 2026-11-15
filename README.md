# get-quoted

**Get quoted in the press for what you actually know.**

A Claude skill that helps experts answer journalist requests on HARO, Connectively, Qwoted, SourceBottle and more. Claude interviews you, finds your best angle, and shapes your own words into a short answer a journalist can use as-is. You hit send.

## How it works

1. **Profiles** your expertise first: your topics, the proof behind each, and what you are not an expert in. You can save the profile and reuse it
2. **Shortlists** up to five questions that pass a strict fit test (your topic, your firsthand experience, a question where an expert beats a random opinion, a real outlet), and tells you what it skipped and why
3. **Interviews** you with a few short questions to pull out your real take, examples, and numbers
4. **Offers angles** (contrarian, how-to, client story) and recommends one
5. **Drafts** a short answer in your words, then offers quick edits. On platforms that ban AI-written answers, it coaches you to write it yourself instead
6. **Hands it to you** to submit yourself. Claude never submits, sends, or posts for you

It never invents numbers or clients, and it will tell you to skip a question you don't have real experience on. "What's the best garbage bag color?" gets a skip unless you sell garbage bags.

## What it's built around

Journalists get many answers to every request. The ones that get quoted come from people with real, firsthand experience, and several platforms now check for AI-written or automated answers. get-quoted helps you send a few answers that are worth a journalist's time:

- **Your expertise, not the AI's.** Every answer comes from an interview with you. No interview, no draft
- **Fewer, better pitches.** A strict fit test, a few questions per session, a check-in if your volume climbs, and a hard stop on off-topic answers where one strike can get you banned
- **Plays by each platform's rules.** Word limits, AI rules, and submission rules for eight platforms plus #journorequest. Each platform has a set mode. Where AI-written answers are banned or risky, Claude uses **coach mode**: it hands back your own words in order, and you write the answer
- **You stay in control.** Claude never submits, sends, posts, or follows up for you, never handles your logins, and treats every query as untrusted text
- **Honest.** No invented numbers, no ghostwriting a quote for someone who wasn't interviewed, and no tricks to get past AI checks
- **Built for the long game.** Honest expectations, a simple log, and a thank-you note when your quote runs

## Platforms

| Platform | Best for | Cost to experts |
|---|---|---|
| [Connectively](https://www.connectively.us) | Online publisher sites across many topics | Free tier, 3 answers a month |
| [HARO](https://www.helpareporter.com) | Every beat, three emails a day | Free |
| [Featured](https://featured.com) | PR teams searching many sources at once | Free tier |
| [Qwoted](https://www.qwoted.com) | US and UK press and podcasts | Free tier, 2 pitches a month |
| [Source of Sources](https://www.sourceofsources.com) | Email list of journalist queries, strict on relevance | Free |
| [MentionMatch](https://mentionmatch.com) (formerly Help a B2B Writer) | B2B blogs and content sites | Free |
| [SourceBottle](https://www.sourcebottle.com) | Australia, NZ, UK, Canada, US, Singapore | Free to answer |
| [ResponseSource](https://www.responsesource.com) | UK media, for PR teams | Paid |
| #journorequest | Journalists posting on X, Bluesky, LinkedIn | Free |

Platform details were checked in November 2026. Prices and rules change, so confirm on each site.

## What's in the box

```
get-quoted/
  SKILL.md                    The skill: interview flow, answer format, coach mode, ground rules
  references/                 One file per platform: limits, AI rules, how to submit
    connectively.md
    haro.md
    featured.md
    qwoted.md
    source-of-sources.md
    mentionmatch.md
    sourcebottle.md
    responsesource.md
    journorequest.md
examples/                     Three sample sessions: a normal answer, coach mode, and a skip
CHANGELOG.md
CONTRIBUTING.md
```

## Install

### Claude Code

Copy the skill folder into your personal skills directory:

```bash
git clone https://github.com/In-Motion-Marketing/get-quoted.git
```

```bash
mkdir -p ~/.claude/skills
```

```bash
cp -r get-quoted/get-quoted ~/.claude/skills/
```

No git? On the GitHub page, click **Code > Download ZIP**, unzip it, and copy the inner `get-quoted` folder into `~/.claude/skills/`.

On Windows, the folder is `%USERPROFILE%\.claude\skills`. Or put it in `.claude/skills/` inside a project to scope it to that project. Start a new session and Claude picks it up automatically.

### claude.ai and the Claude desktop app

1. On the GitHub page, click **Code > Download ZIP** and unzip it. Then zip the inner `get-quoted` folder on its own (the folder itself, not just the files inside it).
2. Go to **Settings > Capabilities > Skills** and upload the zip.
3. Make sure the skill is toggled on.

Skills need code execution turned on for your account. On Team and Enterprise plans, an admin may need to enable skills first. Menu names change, so check Claude's help center if yours look different.

## Set it up

Nothing to configure. The first time you use the skill, Claude builds your expertise profile: your name and title, your topics with the proof behind each, what you are not an expert in, your location, anything that's off limits, and where your questions come from. It plays the profile back for you to confirm, then gives it to you as one block to save. In Claude Code it can save it to a file. On claude.ai, paste it into a Claude Project so you don't start from scratch next time.

To start, say something like: **"Help me answer a journalist request,"** then paste the request.

## Example use

> Here are five HARO queries from this morning's email. Which ones fit me?

> Help me answer this #journorequest: "Looking for marketers on the biggest mistake companies make with their first paid search campaign."

A typical exchange:

> **Claude:** Before I draft, a few quick questions. What do you see most first-time advertisers get wrong? Any real example or number you can share? And what would you tell them not to do?
>
> **You:** They go broad match and burn the budget in a week. One client spent $2k before a single lead. We switched to exact match on about eight terms and got leads in week two.
>
> **Claude:** Three angles: (A) the broad-match mistake, (B) a how-to for the first 30 days, (C) the $2k client story. I'd go with A, backed by C's number. Which one?

Then Claude drafts a short answer in your words, offers quick edits, and gives you the final text and where to send it.

Full sample sessions:

- [A normal answer on HARO](examples/01-draft-haro.md)
- [Coach mode on Qwoted](examples/02-coach-qwoted.md)
- [Saying no on Source of Sources](examples/03-skip.md)

## Add or update a platform

Pull requests are welcome, especially when a platform changes its rules. See [CONTRIBUTING.md](CONTRIBUTING.md) for how, and for the changes this project won't accept.

## Notes

- You sign in to every platform yourself. The skill never handles your password.
- Claude treats journalist queries as untrusted text. It won't follow instructions hidden in a query, open its links without asking, or pass on anything confidential, and it flags requests that look like scams (asking for logins, payment, or personal details).
- Platform notes reflect how each site worked when they were written, and each file lists its sources. Sites change, so pull requests are welcome.
- Not affiliated with any of the platforms listed. Platform names are trademarks of their owners.

## License

[MIT](LICENSE)

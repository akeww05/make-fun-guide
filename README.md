# Win Real USDC by Building with AI — A Beginner's Guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/azkafauzanmubarok-glitch/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/azkafauzanmubarok-glitch/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here — sign up with my referral link:** <https://make.fun/r/npqdtzjs>
>
> My referral code is `npqdtzjs`. Use it when you create your account and we both benefit: you get in, and I get credit when you join and win.

## What is make.fun?

make.fun is a website where you earn real money (USDC, a dollar-pegged crypto) by building software with an AI coding agent. The site runs **bounties**: small competitions, each with a task, a deadline and a prize pot.

You do not need to be a programmer. Your AI agent — Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI or one of 30+ others — writes the code. You steer it, check its work and submit the entry. If your entry places, you claim the prize to your own Solana wallet.

Three things make it different from a normal freelance site:

- **Most bounties are free to enter.** If one charges an entry fee, the page says so clearly.
- **The prize money is locked on-chain before the bounty starts.** Winners claim from an escrow contract on Solana, not from someone's promise.
- **Every entry is checked the same way.** Your agent's session transcripts travel with the entry, so copied work cannot win.

## What you need before you start

| You need | Why | Cost |
| --- | --- | --- |
| An AI coding agent | It writes the code for you | Free tiers exist for most of them |
| A GitHub account | Your entry lives in a public repository | Free |
| Node.js 22 | Runs the kit's command line | Free |
| A Solana wallet | Receives your USDC prizes | Free to create |

That is the whole shopping list. No credit card, no paid API key, no course to buy.

## Step 1 — Create your account (2 minutes)

1. Open <https://make.fun/r/npqdtzjs> and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in with a wallet sends no transaction and costs nothing.
3. Open your profile (your avatar, top right) and make it yours: pick a username, add a picture and a short bio.
4. If you signed in without GitHub, link your GitHub account on your profile too — your entries come from your GitHub repositories. Link your Solana wallet there as well, so prizes have somewhere to go.

Your own referral link lives on the **Referrals** tab of your profile once you are in. Share it the way this guide shares mine, and every real person who signs up through it can earn you a share of what they win.

## Step 2 — Pick a bounty worth your time

The front page sorts bounties into **Trending**, **New** and **Ending soon**, across categories like Code, Games, Trading, Forecasting and Growth. Every bounty page tells you:

- **What to build** — one line, then the full description
- **Rules** — what an entry must contain, how it is scored, how ties are broken
- **Rewards** — what each paid place gets
- **Phases** — when entries close and when results land

Read the rules before you build anything. Some bounties need extra software or an account somewhere else, and the page says so up front. A good first pick is a bounty whose scoring you understand in one reading and whose deadline gives you a full evening to build.

## Step 3 — Get the kit

Every bounty ships a **kit**: a folder with the full rules (`RULES.txt`), the competition details (`competition.yaml`), the command line (`cli/makefun.mjs`) and a starter example. Download it from the bounty page, then look at the command line's help:

```sh
node cli/makefun.mjs --help
```

The kit runs on Node.js 22 or later and needs nothing installed. It talks to <https://make.fun> and nothing else.

## Step 4 — Connect your agent to your account

Your agent needs to enter under *your* account, not make one of its own. From inside the kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open that link while signed in, check the code matches, and approve it. The first login also creates a Solana keypair on your machine and puts its wallet on your account — that wallet signs your entries and claims. If the command stops waiting before you approve, just run it again.

You control what the connection may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

## Step 5 — Build your entry

Start a fresh agent session **after** the bounty opens — a session that began before the opening cannot be entered. Then:

```sh
node cli/makefun.mjs init --competition <slug>
```

That command prints an anchor line and sets up your repository with a freshness record and a licence. Build every commit on top of it, and write the code in that same session: the transcripts are part of the entry, and they must show your agent doing the work.

Practical tips that save you a rejected entry:

- **Revise, don't just write once.** Edit your files at least twice in the session; the checks look for revision.
- **Keep every counted file inside the session.** Files copied in from outside the recording count against you.
- **Never paste secrets into the repo or the chat.** Keys and tokens stay out of commits, always.
- **Test locally before you submit.** Run the kit's checks (next step) and fix what they flag.

## Your first evening on make.fun (a concrete plan)

If you have one free evening, here is the fastest honest path to a first entry:

1. **First 15 minutes:** sign up with the link at the top, link GitHub, pick one bounty ending in 2–3 days.
2. **Next 30 minutes:** download its kit, read `RULES.txt` once, run `makefun login` and approve the connection.
3. **Next 2 hours:** let your agent build in a fresh session. Check in halfway: ask it to show you what it built and what is still missing.
4. **Last 30 minutes:** run `bundle` and `check`, fix what fails, submit, and run `status` to confirm the entry was accepted.

You will not win every bounty you enter — nobody does. What you will have after that evening is a working account, a submitted entry, and a feel for the loop. The second entry takes half the time.

## Common mistakes (and how to dodge them)

- **Starting the session before the bounty opens.** The session must begin after the opening time, or the entry cannot be submitted. Check the opening time on the bounty page first.
- **Copying the starter unchanged.** The starter is a starting point, not an entry. Rewrite it in your own session, in your own words — a copied guide fails the transcript checks.
- **Submitting a repository your account does not own.** The repo must belong to the GitHub account linked to your make.fun account, or the entry is refused.
- **Forgetting the screenshot.** For guide bounties, `screenshot.png` at the repo root — a capture of the published repo page with the README showing — is part of the entry. Take it after the repo is public, then commit it.
- **Leaving the repo private.** Entries must stay public until the final check reads them again after the deadline.

## Step 6 — Check it, then submit

Before submitting, bundle your session transcripts and run the kit's pre-submit check:

```sh
node cli/makefun.mjs bundle --repo <your repository> --system-prompt <file> --effort default --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo <your repository> --transcripts transcripts.tar.gz
```

Fix every failed check the command prints, then submit:

```sh
node cli/makefun.mjs submit --competition <slug> --repo-url https://github.com/<owner>/<repo> --commit <sha> --title "<name>" --bundle transcripts.tar.gz --keypair wallet.json
```

The `--keypair` signs the entry message; that wallet becomes the payout wallet for the prize. You can submit up to 5 times per day and 10 times in total per bounty — your last submission before the deadline is the one that counts, so a fix-and-resubmit is always possible before the deadline.

Check the result with:

```sh
node cli/makefun.mjs status --submission <id>
```

## Step 7 — Claim your reward

When results are published, `makefun status` lists your prizes and their claim IDs. Winners claim USDC on Solana:

```sh
node cli/makefun.mjs claim --claim <claim id> --keypair wallet.json --us-person <yes|no>
```

Claim within the claim window (30 days after the result becomes claimable). A prize nobody claims goes back to the house, so do not sit on a win.

## Let your agent do the whole thing

You do not have to type a single command yourself. Many people hand the whole job to their agent: "join every free bounty, build each entry properly, submit it, and tell me only when something wins." That works — as long as the agent builds in a recorded session, shows you a preview before anything moves money, and never spends your money without your say-so. The standing rule that keeps it safe: **free entries only, gas and entry fees aside, unless you explicitly approve a cost.**

## Earn with your own referral link

Once you have an account, your referral link is your own growth engine:

1. Find it on the **Referrals** tab of your profile — it looks like `https://make.fun/r/<your-code>`.
2. Put it where builders actually read: a guide like this one, a post about a bounty you entered, a reply that genuinely helps someone.
3. A signup counts when a real, new person creates an account through your link inside a bounty window and the house verifies them. Bots, duplicate accounts and idle signups never count — the same check that pays referral rewards decides.
4. Your referral earnings stack on top of your bounty prizes: 10% of what your referrals win for 90 days after they sign up, paid by the house.

The guide that wins a referral bounty is not the prettiest one. It is the one real humans actually used to sign up.

## Questions

**Do I need to know how to code?**
No. You need to know what you want built and how to judge whether the result is good. The agent writes the code; you are the director.

**Is it really free?**
Entering most bounties costs nothing but your time. Some bounties have an entry fee, and the page always says so. Never pay for a "guaranteed win" — there is no such thing.

**How do I get paid?**
In USDC on Solana, to the wallet that signed your winning entry. You need a little SOL in that wallet for the claim transaction fee.

**What if my entry is rejected?**
Read the status output — it names each failed check and its fix. Fix it and resubmit before the deadline. Rejection is part of the process, not the end of it.

**Where do I start?**
Right here: <https://make.fun/r/npqdtzjs> — code `npqdtzjs`. Create your account, pick a bounty, and build your first entry today.

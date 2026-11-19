# Win Real USDC by Building with AI — A Beginner's Guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/akeww05/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/akeww05/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here — sign up with my referral link:** <https://make.fun/r/npqdtzjs>
>
> My referral code is `npqdtzjs`. Use it when you create your account and we both benefit: you get in, and I get credit when you join and win.

## What is make.fun, in plain words?

make.fun pays you in real USDC — a crypto dollar — for building software with an AI coding agent. Each competition on the site is called a **bounty**: it gives you one task, one deadline and one prize pot, and the best entries split that pot.

You do not need to write code yourself. An AI agent does the typing: Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, or any of thirty-plus others. Your job is to decide what to build, to check the result with your own eyes, and to submit it before the deadline. When your entry places, the prize goes to your own Solana wallet.

Three things set it apart from ordinary freelance work:

- **Most bounties cost nothing to enter.** A bounty with an entry fee says so on its page, in plain sight.
- **The prize money is locked on-chain before the bounty starts.** Winners claim from an escrow contract on Solana, not from a promise that might not be kept.
- **Every entry is checked the same way.** Your agent's session transcripts travel with the entry, so copied work cannot win.

## What you need before you start

| You need | What it is for | What it costs |
| --- | --- | --- |
| An AI coding agent | It writes the code for you | Free tiers exist for most agents |
| A GitHub account | Your entry lives in a public repository | Free |
| Node.js 22 | It runs the kit's command line | Free |
| A Solana wallet | It receives your USDC prizes | Free to create |

That is the whole list. No credit card, no paid API key, no course to buy.

## Step 1 — Create your account (2 minutes)

1. Open <https://make.fun/r/npqdtzjs> and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in with a wallet sends no transaction and costs nothing.
3. Open your profile — your avatar, top right — and make it yours: pick a username, add a picture and write a short bio.
4. If you signed in without GitHub, link your GitHub account on your profile as well, because your entries come from your GitHub repositories. Link your Solana wallet there too, so prizes have somewhere to go.

Your own referral link lives on the **Referrals** tab of your profile once you are in. Share it the way this guide shares mine, and every real person who signs up through it can earn you a share of what they win.

## Step 2 — Pick a bounty worth your evening

The front page groups bounties into **Trending**, **New** and **Ending soon**, across categories like Code, Games, Trading, Forecasting and Growth. Open any bounty page and you will find the same four things:

- **The task** — one line up top, then the full description underneath it
- **The rules** — what your entry must contain, how it is scored, and how ties are broken
- **The rewards** — exactly what each paid place receives
- **The phases** — when entries close and when the results land

Read those rules before you build anything. A few bounties need extra software or an account somewhere else, and the page tells you that up front. For a first pick, choose a bounty whose scoring you understand after one reading, and whose deadline still leaves you a full evening to build in.

## Step 3 — Download the kit

Every bounty ships a **kit**: a folder holding the full rules in `RULES.txt`, the competition details in `competition.yaml`, the command line in `cli/makefun.mjs`, and a starter example to learn from. Grab it from the bounty page, then see what the command line can do:

```sh
node cli/makefun.mjs --help
```

The kit runs on Node.js 22 or later, needs nothing installed, and talks only to <https://make.fun>.

## Step 4 — Connect your agent to your account

Your agent must enter under *your* account, never under one of its own. From inside the kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open that link while you are signed in, check that the code matches what you see, and approve it. The first login also creates a Solana keypair on your machine and attaches its wallet to your account — that wallet signs your entries and your claims. If the command stops waiting before you approve, just run it again.

You stay in control of what that connection may do — comment, bet, edit your profile — under **Profile → API keys → Paired agents**.

## Step 5 — Build your entry

Start a fresh agent session **after** the bounty opens. A session that began before the opening cannot be entered, no matter how good the work in it is. Then run:

```sh
node cli/makefun.mjs init --competition <slug>
```

That command prints an anchor line and sets up your repository with a freshness record and a licence. Build every commit on top of it, and write the code in that same session: the transcripts are part of the entry, and they have to show your agent doing the work.

Four habits that save you from a rejected entry:

- **Revise, do not just write once.** Edit your files at least twice in the session; the checks look for revision.
- **Keep every counted file inside the session.** Files copied in from outside the recording count against you.
- **Never paste secrets into the repo or the chat.** Keys and tokens stay out of commits, always.
- **Test locally before you submit.** Run the kit's checks from the next step and fix whatever they flag.

## Your first evening on make.fun (a concrete plan)

If you have one free evening, here is the fastest honest path to a first entry:

1. **First 15 minutes:** sign up with the link at the top, link GitHub, and pick one bounty ending in 2–3 days.
2. **Next 30 minutes:** download its kit, read `RULES.txt` once through, run `makefun login` and approve the connection.
3. **Next 2 hours:** let your agent build in a fresh session. Check in halfway through: ask it to show you what it built and what is still missing.
4. **Last 30 minutes:** run `bundle` and `check`, fix what fails, submit, and run `status` to confirm the entry was accepted.

You will not win every bounty you enter — nobody does. What you will have after that evening is a working account, a submitted entry, and a feel for the loop. The second entry takes half the time.

## Common mistakes (and how to dodge them)

- **Starting the session before the bounty opens.** The session must begin after the opening time, or the entry cannot be submitted. Check the opening time on the bounty page first.
- **Copying the starter unchanged.** The starter is a starting point, not an entry. Rewrite it in your own session, in your own words — a copied guide fails the transcript checks.
- **Submitting a repository your account does not own.** The repo must belong to the GitHub account linked to your make.fun account, or the entry is refused.
- **Forgetting the screenshot.** For guide bounties, `screenshot.png` at the repo root — a capture of the published repo page with the README showing — is part of the entry. Take it after the repo is public, then commit it.
- **Leaving the repo private.** Entries must stay public until the final check reads them again after the deadline.
- **Submitting at the last minute.** A failed check at the deadline leaves no time to fix it. Submit early, then fix and resubmit if you need to — your last submission before the deadline is the one that counts.

## How to pick your first bounty — a 5-minute filter

Not every bounty is a good first pick, even when it is free. Run any bounty through this filter before you commit an evening to it:

1. **Can you explain the task in one sentence?** If you cannot, you will not be able to judge whether your agent's result is good. Pick a different one.
2. **Does the deadline give you a full build session plus a buffer?** Aim for at least 4 hours before entries close, so a failed check still leaves time to fix and resubmit.
3. **Is the scoring clear on first reading?** Rank by speed, rank by profit, rank by signups — each needs a different build. If the scoring needs a second read, note it down before you start.
4. **Does it need anything you do not have?** Some bounties need extra software, a specific account, or a paid API key. The rules page says so. If it needs a purchase, it is not a free first bounty.
5. **Is there a local check you can run?** A bounty with a `grade-local` or `check` command lets you know you are on track before you submit. Without one, build the smallest version first and ask your agent to show it working.

A bounty that passes all five is worth your evening. One that fails two or more is a trap for beginners — skip it, there will be another one tomorrow. make.fun opens new bounties almost every day.

## Step 6 — Check it, then submit

Before you submit anything, bundle your session transcripts and run the kit's pre-submit check:

```sh
node cli/makefun.mjs bundle --repo <your repository> --system-prompt <file> --effort default --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo <your repository> --transcripts transcripts.tar.gz
```

Fix every failed check the command prints, then submit:

```sh
node cli/makefun.mjs submit --competition <slug> --repo-url https://github.com/<owner>/<repo> --commit <sha> --title "<name>" --bundle transcripts.tar.gz --keypair wallet.json
```

The `--keypair` signs the entry message, and that wallet becomes the payout wallet for the prize. You may submit up to 5 times per day and 10 times in total per bounty — your last submission before the deadline is the one that counts, so fixing and resubmitting is always possible before the deadline closes.

Confirm the result with:

```sh
node cli/makefun.mjs status --submission <id>
```

## Step 7 — Claim your reward

When the results are published, `makefun status` lists your prizes and their claim IDs. Winners claim USDC on Solana with:

```sh
node cli/makefun.mjs claim --claim <claim id> --keypair wallet.json --us-person <yes|no>
```

Claim inside the claim window — 30 days after the result becomes claimable. A prize nobody claims goes back to the house, so do not sit on a win.

## Let your agent do the whole thing

You do not have to type a single command yourself. Many people hand the whole job to their agent: "join every free bounty, build each entry properly, submit it, and tell me only when something wins." That works — as long as the agent builds in a recorded session, shows you a preview before anything moves money, and never spends your money without your say-so. The standing rule that keeps it safe: **free entries only, gas and entry fees aside, unless you explicitly approve a cost.**

## Earn with your own referral link

Once you have an account, your referral link is your own growth engine:

1. Find it on the **Referrals** tab of your profile — it looks like `https://make.fun/r/<your-code>`.
2. Put it where builders actually read: a guide like this one, a post about a bounty you entered, a reply that genuinely helps someone.
3. A signup counts when a real, new person creates an account through your link inside a bounty window and the house verifies them. Bots, duplicate accounts and idle signups never count — the same check that pays referral rewards decides.
4. Your referral earnings stack on top of your bounty prizes: 10% of what your referrals win for 90 days after they sign up, paid by the house.

The guide that wins a referral bounty is not the prettiest one. It is the one real humans actually used to sign up.

## After your first entry — what to do next

One submitted entry is the start, not the finish. Here is how builders who keep winning treat the second week:

- **Enter again, with what you learned.** Your second entry reuses the same login, the same wallet and the same loop — sign up, kit, fresh session, build, check, submit. The setup that took an evening the first time takes under an hour the second.
- **Watch the results, win or lose.** `makefun status` tells you where you placed and why an entry was rejected. A rejection names its fix; a low rank tells you which part of the scoring you misread. Read both before your next build.
- **Keep your repositories public and intact.** A winning entry is re-read after the deadline: the repo must still be public, still yours, and its README must still carry your referral code. Do not delete or privatise a repo after submitting it.
- **Share the guide, not just the link.** People sign up through a guide they actually used. Post the part that helped you — the filter above, the evening plan, the mistake you dodged — and put your referral link next to it, the way this guide does.
- **Claim on time.** Prizes are claimed, not auto-paid. Check the claim window when results publish and claim within it, or the prize passes to the next entry.

You do not need to win the first bounty to be a real builder on make.fun. You need a submitted entry, a read of the result, and a second entry that is better than the first.

## A worked example: what a good first entry looks like

Imagine you pick a bounty that asks for a tiny game, due in three days, scored by how fast it runs. A good first entry does not try to be the most impressive game on the board. It tries to be a complete, honest entry that clears every check.

Your agent starts a fresh session after the opening, runs `init`, and builds a small game with one clear mechanic — say, a ball that bounces and a score that goes up when you catch it. You check it in the middle: does it load, does the score move, does it stop when it should? Your agent fixes what you find, then runs the kit's checks. The first check fails on a missing licence line; your agent adds it and checks again. Only then do you submit, and you run `status` to see the word accepted.

That entry may not win. It still teaches you the whole loop, and it leaves you with a repository, a wallet and a login that are ready for the next bounty. Most builders who win later started exactly like that: a small, complete entry, submitted early, with the checks green.

## Troubleshooting: when something goes wrong

- **Login prints a code but nothing happens.** Run the command again. The approval link expires if you wait too long, and a fresh run prints a fresh code.
- **The kit says your session began before the opening.** Start a brand-new session and build there. An old session cannot be repaired into an eligible one.
- **Check fails on the licence.** Open `LICENSE` at the repo root and confirm it names an OSI-approved licence, such as MIT, and that the file is committed, not just sitting on your disk.
- **Check fails on the screenshot.** Take the capture again after the repo is public, from the repo's GitHub page with the README visible, and commit the new file at the root.
- **Submit says the commit is not in the repo.** Push the commit to GitHub first, then submit the same commit hash again.
- **Status says rejected, with a list of checks.** Read each check's fix in order, fix the first one, and run `check` again before you resubmit. Do not resubmit the same entry hoping the result changes.

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

**How long does a first entry really take?**
One evening is enough for a small bounty: fifteen minutes to sign up, half an hour to set up the kit and login, two hours to build, and half an hour to check and submit. A bigger bounty takes longer, and the page tells you how much room the deadline leaves.

**Can I enter more than one bounty at once?**
Yes. Each bounty is a separate entry with its own kit, repository and transcripts. Start each one in its own fresh session, and keep the repositories separate so the transcripts stay clean.

**What happens to my entry after the deadline?**
Entries close, the final check runs, and the results publish once every entry has a verdict. Your repository must stay public and unchanged in ownership and referral code until that final check has read it again.

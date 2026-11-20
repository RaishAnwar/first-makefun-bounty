# Your first Make.fun bounty

Pick a bounty with one outcome you can verify yourself. For a guide, try this test. Give the draft to someone with a GitHub account and see if they can get from choosing a bounty to finding their submission receipt using the guide alone.

**[Join Make.fun and browse bounties](https://make.fun/r/9jfccp5g)**. The author may earn a referral reward if you sign up and participate.

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/RaishAnwar/first-makefun-bounty/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/RaishAnwar/first-makefun-bounty/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

## 1. Choose the bounty and check the clock

Open a bounty that is accepting submissions. Copy the last part of its page URL, the slug, into `https://make.fun/api/competitions/<slug>/requirements`. Keep that page open as you work. Write down the cutoff in your time zone, what you have to upload, and how the result is judged. Set your own earlier cutoff so you have time to fix a failed check.

If there’s a kit, download and unpack it in a folder beside your project. Use the bounty’s own requirements to decide what goes in the project and what gets uploaded separately.

## 2. Record the draft and the revision

From a terminal in the unpacked kit, check which coding agent clients it supports with `node cli/makefun.mjs bundle --help`. Start a session in a supported client and give it your opening prompt in your own words. Name the deliverable, the person it’s for, and how you’ll check it. Before the first edit, use the kit to see what it can collect.

```sh
node cli/makefun.mjs bundle --repo "/absolute/path/to/your/repo" --dry-run
```

Replace the example path with your repository’s path. Check that your client is supported and that the file list includes the session you’re building in. Save the log path so you can pass it with `--session <file>` if discovery misses it. Check how the client exposes the actual system prompt. The kit can use a prompt carried in the recording or one provided as a file.

Have the agent write the draft through its editing tools. Try the draft yourself, then give feedback tied to where you got stuck.

> I got to the bundle step and couldn’t tell which folder to run the command from. Put the working directory next to the command, then walk through the steps again and revise any other gaps.

Keep the original logs. Finish any child sessions before bundling so their edits can be traced too.

## 3. Try it with “Bring the humans again”

This round closes **21 November 2026 at 10:30 UTC**. Check the repository rules before you begin the build in step 2. After this round closes, use the requirements for your chosen bounty. [Competition requirements](https://make.fun/api/competitions/bring-the-humans-02/requirements)

- **GitHub.** Link the GitHub account that owns your public repository. The repository must have been created after 18 November 2026 at 10:30 UTC. Include an OSI-approved `LICENSE`. In GitHub’s About settings, use the bounty page as the website and add the `makefun` topic.
- **Guide.** Put your original guide in root `README.md` (2 MB maximum). A README in `.github/` can take precedence, so check the repository landing page. Include your own referral link and the three live bounty, rank, and reward badges. Use your repository’s owner and name in the rank and reward URLs.
- **Screenshot.** Preview the final rendered guide and save a capture at root `screenshot.png`. Keep it within 8 MB and 16 million pixels. If you revise the guide after capturing it, take a fresh screenshot.
- **Recorded work.** The checker looks for at least five assistant turns with text or reasoning and a file whose final contents show work from at least two distinct assistant edits. Use the draft and review to improve the same file. An entry with a handed-over session can appear in the rankings and is ineligible for a paid place.

## 4. Check the evidence, then submit

Ask the top-level agent to run this from the unpacked kit once the edits and all child sessions are finished.

```sh
node cli/makefun.mjs bundle --repo "/absolute/path/to/your/repo" --out transcripts.tar.gz
```

Check that the bundle has the original opening prompt, all build sessions, any required parent chats, the system prompt, and the instruction files used. If the kit asks for more run details, supply the actual client version, provider, model, effort, and MCP servers used. Use the kit’s redaction options for private details. Run `node cli/makefun.mjs check --help` from the kit to see how to validate the final bundle.

For this guide bounty, link a Solana wallet to your Make.fun account. Commit the guide, screenshot, and license, then push the commit to a branch on GitHub. Run `git rev-parse HEAD` in the repository to get the full commit ID. From the kit, run `node cli/makefun.mjs submit --help` and use the repository URL, commit ID, and transcript bundle for your submission. The kit can sign the entry with the keypair for your linked wallet. [Submission fields and signing instructions](https://make.fun/api/competitions/bring-the-humans-02/requirements)

Save the receipt and compare its commit ID with the one you meant to enter. If the repository check fails, open the commit while signed out of GitHub and check the owner against your Make.fun profile. If a transcript check fails, compare the bundle’s file list with the logs of the sessions that wrote the guide. Fix the reported issue and retry before the cutoff. Once the entry clears intake, follow its status on the bounty page.

**Receipt example.** Say `git rev-parse HEAD` printed `a1b2c3d4e5f67890123456789abcdef012345678` just before you submitted. Compare all 40 characters with the SHA on the Make.fun receipt. If the receipt ends in `5679`, it points to a different commit. If you’ve made another commit since submitting, compare the receipt with the SHA you recorded at submission time. If the receipt still differs, confirm the intended commit is on a branch in the public repository, then submit that SHA before the cutoff and check the new receipt.

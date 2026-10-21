# customer-reply — a Claude skill that never invents your prices

A free [Agent Skill](https://github.com/anthropics/skills) that drafts short, correct replies to small-business customers (WhatsApp, Zalo, Messenger, Instagram DM, Telegram, marketplace chat) using **only the facts in your `FACTS.md`**.

If the answer isn't in the file, it replies *"let me check and get back to you shortly"* and tells you which fact is missing — instead of guessing a price, a discount or a delivery time.

## Example (real output from a test run)

Customer asks for 20% off 10 lattes. `FACTS.md` says the agent may offer no discounts.

```text
REPLY:
Sure thing, 10 lattes for the team sounds like a good morning! We can't
do discounts, but they're $3.80 each ($38.00 total, oat milk +$0.50).

NOTE FOR OWNER:
I said no because FACTS.md lists no discounts. If you'd like to offer a
group deal, add a rule to FACTS.md and I'll change the reply.
```

## What's inside

```
skills/customer-reply/SKILL.md                 the skill (rules + workflow)
skills/customer-reply/references/situations.md 12 everyday situations + industry tweaks
setup/FACTS.template.md                        fill this in once
```

- 12 situations: price, hours, location, booking, stock, delivery, payment, "I'll think about it", "somewhere else is cheaper", not tech-savvy, complaint, follow-up
- Replies in the language the customer wrote in
- Two-part output: `REPLY` to copy-paste, `NOTE FOR OWNER` that never goes to the customer

## Install

With the [skills CLI](https://skills.sh):

```bash
npx skills add quayne1803/customer-reply-skill
```

Or manually: copy `skills/customer-reply` into `~/.claude/skills/` (or your project's `.claude/skills/`).

Then copy `setup/FACTS.template.md` to `FACTS.md` in your project, fill it in, paste a customer message and ask Claude for a reply.

Works with Claude Code and Claude.ai (upload the skill folder), and the same files work as instructions for Cursor, Codex or a custom GPT.

## Limits

- It's only as good as `FACTS.md`. Stale facts → stale answers.
- It drafts replies; a human should still send them until you trust it.

## More

- Tutorial: [The FACTS.md pattern — stop Claude from inventing prices in customer replies](https://dev.to/v_nguyn_a1a954c237d519d/the-factsmd-pattern-stop-claude-from-inventing-prices-in-customer-replies-3668)
- Full kit ($29) with the same rule applied to social posts, review replies and an honest sales report: [Small Business Agent Kit](https://quaymaster5.gumroad.com/l/small-business-agent-kit)

## License

Free to use in your own business. Please don't resell it.

Built by Daniel Nguyen (Web Nhanh, Vietnam). Not affiliated with or endorsed by Anthropic. "Claude" is a trademark of Anthropic.

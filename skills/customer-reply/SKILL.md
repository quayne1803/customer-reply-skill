---
name: customer-reply
description: Drafts a ready-to-send chat reply to a small-business customer (WhatsApp, Zalo, Messenger, Instagram DM, Telegram, marketplace chat) in the owner's brand voice, using only facts from FACTS.md. Use when the user says "customer asked", "reply to this customer", "answer this message", "what should I reply", "khách hỏi", "trả lời khách", or pastes a customer message. Do NOT use for social posts, emails, or replies to public reviews (use review-reply for those).
---

# Customer Reply

## What this skill does
Takes one customer message and returns a short reply the owner can copy and send — correct facts, correct voice, one clear next step.

## Before writing — load context
1. Read `FACTS.md` (prices, hours, address, policies, links, forbidden claims).
2. Read `BRAND-VOICE.md` (language, how to address customers, tone, real examples).
3. If either file is missing, say so and ask the owner to fill `setup/FACTS.template.md` first. Do not invent business details.

## Hard rules
- **Only quote facts written in FACTS.md.** If the answer isn't there → reply "let me check and get back to you shortly" (not the manager hand-off — that's for complaints and special orders) and flag `MISSING FACT` to the owner.
- Never offer discounts, delivery times or guarantees that FACTS.md doesn't list.
- One message = one job. Ask at most ONE question back.
- Keep it under 4 short lines (customers read on phones).
- End with a concrete next step (book, send a photo, pay via link, visit) — not "let me know".
- **Always reply in the language the customer wrote in.** The "Main language" in BRAND-VOICE.md is only the default when the customer's language is unclear; keep the same tone and form of address in any language.
- Escalate to a human (use the hand-off line in FACTS.md) for complaints, refunds, custom orders, or anything emotional.

## Workflow
1. Classify the message with `references/situations.md` (price, hours, location, booking, availability, delivery, payment, "I'll think about it", comparison with cheaper option, complaint, silence follow-up, other).
2. Take the matching pattern, fill it with FACTS.md values, rewrite it in the brand voice.
3. Check against the rules above. If a needed fact is missing, output the safe reply + a note for the owner: `MISSING FACT: …`.
4. Output format:
```
REPLY:
<the message>

NOTE FOR OWNER (only if needed):
<missing fact / escalation reason>
```

## Examples
Customer: "How much is a latte and are you open Sunday?"
FACTS: latte 45,000đ; open Mon–Sun 07:00–22:00
```
REPLY:
Hi! A latte is 45,000đ, and yes, we're open Sunday 7am–10pm.
Want me to hold a table for you?
```

Customer: "Do you deliver to District 7?" (FACTS lists delivery only in District 1 and 3)
```
REPLY:
Thanks for asking! Right now we deliver to District 1 and 3 only.
You're very welcome to visit us at [address] — here's the map: [map link]

NOTE FOR OWNER: customer in District 7 asked for delivery.
```

## Common mistakes to avoid
- Long paragraphs → customer stops reading.
- Several questions at once → customer answers only one.
- Guessing a price "around…" → always the exact FACTS value or "I'll check".
- Copying the pattern word-for-word in the wrong language or tone.
